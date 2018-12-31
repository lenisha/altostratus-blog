+++
banner = ""
categories = ["terraform"]
date = "2018-11-146T12:10:51+02:00"
description = ""
images = []
menu = ""
tags = ["terraform","tips and tricks"]
title = "Terraform for custom tasks - invoking anc capturing shell scripts"
+++

Using Terraform with Azure Resource Provider for supported resources is very straightforward, there are cases when we need to invoke features that have not been enabled by ARM yet - for example the ones that are in preview.
When working on terraforming the infratructure for static web sites, I have encountered just this problem - enabling static website funtionality for Azure storage which is currently in preview could be only done thru REST call or az cli.


<!--more-->

Read full article at [Open Source Microsoft](https://cloudblogs.microsoft.com/opensource/2018/11/16/terraform-jamstack-azure-gatsby-azure-pipelines-git/)


