+++
banner = ""
categories = ["terraform", "azure devops"]
date = "2018-05-22T11:58:06+02:00"
description = "Building you own Azure Devops(VSTS) agent with Terrfaorm/Ansible/Packer tools and running it on Azure ACI"
images = []
menu = ""
tags = ["azure devops","terraform","ansible","aci", "docker"]
title = "How to create a custom Azure Devops agent on Azure ACI with Terraform"
+++

Open source tools, like [Terraform][1] and [Ansible](https://www.ansible.com/), can be leveraged to implement [“infrastructure as code”](https://docs.microsoft.com/en-us/azure/devops/what-is-infrastructure-as-code) making it easier to continuously build and deploy cloud infrastructure across your applications.

Azure Devops (previously VSTS) provides automated pipelines to build, test, and deploy your code to any platform. It uses agents to perform build and release tasks. Creating private agents has the advantage of being able to install the specific software needed for the builds.

<!--more-->
To use HashiCorp and Ansible tools for Azure build and release tasks, we will configure a private VSTS agent with a prepared image hosted [on DockerHub](https://hub.docker.com/r/lenisha/vsts-agent-infrastructure/)). This image is based on the Microsoft standard [VSTS agent image](https://hub.docker.com/r/microsoft/vsts-agent/) and extends it with installed Terraform, Packer and Ansible tools.

To make solution more lightweight and to minimize costs for running the agent, we’ll show you how to provision a custom VSTS agent on Azure Container Instance (ACI) — a service that became [generally available](https://azure.microsoft.com/en-us/blog/azure-container-instances-now-generally-available/) this month. ACI provides an easy way to run containers on Azure.

Read full article at [Open Source Microsoft](https://cloudblogs.microsoft.com/opensource/2018/05/22/how-to-create-vsts-agent-azure-aci-terraform/)


 [1]: https://www.terraform.io/
