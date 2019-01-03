+++
banner = "images/devops-terraform-ansible/terraform-ansible.png"
categories = ["terraform", "azure devops"]
date = "2018-05-22T12:10:51+02:00"
description = "Building CI/CD for SpringBooot Application with Azure Devops and Ansible, Terraform"
images = ["images/devops-terraform-ansible/terraform-ansible.png"]
menu = ""
tags = ["azure devops","terraform","ansible", "springboot", "azure vmss"]
title = "CI/CD for Azure using Terraform, Ansible and Azure Devops"
+++

This is part 1 of a 2-part series demonstrating how to continuously build and deploy Azure infrastructure for the applications running on Azure. The first article will show how open source tools, such as [Terraform][1] and [Ansible](https://www.ansible.com/), can be leveraged to implement Infrastructure as Code. The second article in the series will enhance the infrastructure deployment to build immutable infrastructure for the applications and adding Packer into the set of tools.

In part 1, we will walk though how to continually build and deploy a Java Spring Boot application and its required infrastructure and middleware using [Azure Devops](https://visualstudio.microsoft.com/team-services/) (previously VSTS). We will apply software development practices to infrastructure build and configuration. To demonstrate Infrastructure as a Code principle we will use Terraform to codify and provision infrastructure, and Ansible to automate configuration and middleware.
<!--more-->

Read full article at [Open Source Microsoft](https://cloudblogs.microsoft.com/opensource/2018/05/22/cicd-azure-terraform-ansible-vsts-java-springboot-app/)



 [1]: https://www.terraform.io/

