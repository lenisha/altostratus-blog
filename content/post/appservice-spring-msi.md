+++
banner = "images/appsrv-msi/appsrvc-msi.png"
categories = ["azure appservice", "java"]
date = "2018-11-08T11:58:06+02:00"
description = "This tutorial demonstrates lift and shift in the cloud by migrating a Java legacy application and removing credentials from the code."
images = []
menu = ""
tags = ["azure appservice","msi","java","spring", "datasource", "managed service identity"]
title = "Migrating Java Applications to Azure App Service (Part 1 - DataSources and Credentials)"
+++

Running on the cloud is not only for cool new applications following [12-factor](https://12factor.net/) principles and coded to be cloud-native. Many applications could be converted to be cloud-ready with minimal adjustments — just to be able to run in the cloud environment. In the following few articles we will demonstrate how to address the most common migration items in legacy Spring applications — handling JNDI, and credentials, externalizing configuration, remote debugging, logging, and monitoring.

This article demonstrates how to migrate Java Spring/Hibernate applications using JNDI settings to cloud environment, externalize configuration, and how to keep credentials out of code by using [Azure Managed Service Identity](http://docs.microsoft.com/azure/active-directory/msi-overview).

Read full article at [DZone](https://dzone.com/articles/migrating-java-applications-to-azure-app-service-p)


