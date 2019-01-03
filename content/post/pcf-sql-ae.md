+++
banner = "images/pcf-sql-ae/pcf-sql-ae.png"
categories = ["pcf", "azure sql", "java"]
date = "2018-11-16T11:58:06+02:00"
description = "This article demonstrates how to secure Java Spring Boot application data with Azure SQL Always Encrypted running on PCF"
images = ["images/pcf-sql-ae/pcf-sql-ae.png"]
menu = ""
tags = ["azure sql","pcf","cloud foundry","springboot", "alwaysencrypted"]
title = "Azure SQL with PCF Spring Boot Applications (Part 2 - AlwaysEncrypted)"
+++

This is part 2 of the series demonstrating advanced[Azure SQL](https://azure.microsoft.com/en-ca/services/sql-database/) (PAAS) features and how to use them from Java Spring Boot applications running on [PCF](https://pivotal.io/platform) (Pivotal CloudFoundry) (Pivotal CloudFoundry) on Azure. The [first article](https://dzone.com/articles/pcf-spring-boot-applications-using-azure-sql-part) showed how to use a Spring Boot application with Azure SQL Database auto-failover groups to provide resilience to regional outages and walked thru Azure Service Broker providing seamless integration with Azure services to applications running Pivotal CloudFoundry.

This article will demonstrate how to protect sensitive data (such as password, credit cards, and social security numbers) in Azure SQL database. Security and protection of the data becomes even more important to enterprises looking to migrate databases to the cloud. The Always Encrypted feature of Azure SQL enables customers to be confident that even high privileged but unauthorized users cannot access their encrypted data in the cloud. It safeguards data not only “at-rest” and ”in transit”, but also "in use” in any data lifecycle event and does it transparently to applications. Moreover, encryption keys are not stored within the database, they stay with the client (in the demo below — stored in Key Vault) and that’s why it keeps data protected even from cloud operators.

Read full article at [DZone](https://dzone.com/articles/azure-sql-with-pcf-spring-boot-applications-part-2)


