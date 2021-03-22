+++
banner = "images/terra-custom/terraform-custom.png"
categories = ["terraform"]
date = "2018-11-14T12:10:51+02:00"
description = "How to use custom provisioning scripts in Terraform to enable features that are not yet supported by provider."
images = ["images/terra-custom/terraform-custom.png"]
menu = ""
tags = ["terraform"]
title = "Terraform for custom tasks - invoking anc capturing shell scripts"
+++

Using Terraform with Azure Resource Provider for supported resources is very straightforward, there are cases when we need to invoke features that have not been enabled by Terraform provider yet.
In this post I will summarize the tweaks to make custom provisioning actions work by using `local-exec` provisioner and bash scripts inside Terraform resources.

<!--more-->

For the article on hosting [JAMStack](https://cloudblogs.microsoft.com/opensource/2018/11/16/terraform-jamstack-azure-gatsby-azure-pipelines-git/) on Azure
I need to enable the [Static Website](https://azure.microsoft.com/en-ca/blog/azure-storage-static-web-hosting-public-preview/) feature as it is currently only supported though Azure CLI or API. (No ARM or Terraform support yet). 
To do configuraion tasks thare are number of provisioners available in Terraform (Ansible, Salt etc). For simple script invocation  `local-exec` provisioner is what we need. Here is the snippet that runs the Azure CLI command to enable the static website for storage:
```
resource "azurerm_storage_account" "webblob" {
  name                     = "${var.dns_name}"
  location                 = "${azurerm_resource_group.demo-rg.location}"
  resource_group_name      = "${azurerm_resource_group.demo-rg.name}"
  account_kind             = "StorageV2"
  account_tier             = "Standard"
  account_replication_type = "LRS"

   provisioner "local-exec" {
    command = "az storage blob service-properties update --account-name ${azurerm_storage_account.webblob.name} --static-website  --index-document index.html --404-document 404.html"
  }
}
```

Once the command is run it is often that we need to capture the result and make it managed by Terraform state to enable next runs or provide result as an input to other resources. 
In our example once static website is enabled it provides the read only endpoint URL to access the website, that will be used by Azure CDN as origin. 
Fortunately, there is a great Terraform Shell Resource Module available that helps to manage the output of shell commands inside Terraform https://registry.terraform.io/modules/matti/resource/shell/0.3.1. Here is the code example that queries the Storage account to get the endpoint:
```
module "query_url" {
  source  = "matti/resource/shell"

  command = "printf $(az storage account show -n ${azurerm_storage_account.webblob.name} -g ${azurerm_resource_group.demo-rg.name} --query \"primaryEndpoints.web\" --output tsv | cut -d \"/\" -f 3)"
}
```
Now we can use the reults in other dependent resources for example provision Azure CDN and CDN Endpoint pointing to our Static Website URL:
```
resource "azurerm_cdn_endpoint" "webblob-cdn-endpt" {
  name                = "${var.dns_name}"
  profile_name        = "${azurerm_cdn_profile.webblob-cdn.name}"
  location            = "${azurerm_resource_group.demo-rg.location}"
  resource_group_name = "${azurerm_resource_group.demo-rg.name}"
  is_http_allowed     = "false"
  optimization_type   = "GeneralWebDelivery"
  origin_host_header  = "${module.query_url.stdout}"
  querystring_caching_behaviour = "IgnoreQueryString"
  
  origin {
    name      = "assets"
    host_name = "${module.query_url.stdout}"
    https_port = "443"
  }
  depends_on = ["module.query_url"]
}
```

