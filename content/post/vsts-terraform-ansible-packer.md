+++
banner = "images/devops-terraform-ansible-packer/terraform-ansible-packer.png"
categories = ["terraform", "azure devops"]
date = "2018-05-23T12:10:51+02:00"
description = "Building CI/CD for immutable infrastructure with Azure Devops and Terraform, Ansible, Packer"
images = ["images/devops-terraform-ansible-packer/terraform-ansible-packer.png"]
menu = ""
tags = ["azure devops","terraform","ansible","packer","springboot", "azure vmss"]
title = "Immutable infrastructure for Azure, using Azure Devops, Terraform, Packer and Ansible"
+++

This is part 2 of a 2-part series on CI/CD for [“infrastructure as code”](https://docs.microsoft.com/en-us/azure/devops/what-is-infrastructure-as-code) on Azure. [In part 1](https://open.microsoft.com/2018/05/22/cicd-azure-terraform-ansible-vsts-java-springboot-app/), we covered a basic pipeline building application and provisioning infrastructure codified as Terraform templates and Ansible playbooks. While it demonstrated how infrastructure is treated as a code – stored, versioned, and audited – there is still room for configuration drifts and the time required to update the configuration on the server could make auto-scaling challenging. Configuration updates using Ansible also require SSH ports to be open. These and some other considerations are addressed in this tutorial.
Below we’ll demonstrate how to build immutable infrastructure for Azure using [Azure Devops](https://visualstudio.microsoft.com/team-services/) (previously VSTS) as continuous integration and delivery (CI/CD) and popular HashiCorp and Red Hat tools.

<!--more-->

Read full article at [Open Source Microsoft](https://cloudblogs.microsoft.com/opensource/2018/05/23/immutable-infrastructure-azure-vsts-terraform-packer-ansible/)



 [1]: https://www.terraform.io/

