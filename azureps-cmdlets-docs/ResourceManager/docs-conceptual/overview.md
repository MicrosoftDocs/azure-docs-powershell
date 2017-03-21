---
title: Overview of the Azure PowerShell | Microsoft Docs
description: An overview of Azure PowerShell with links to installation and configuration.
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sewhee
ms.manager: carmonm
---

# Overview of the Azure PowerShell

Azure PowerShell provides a set of cmdlets that use the Azure Resource Manager model for managing
your Azure resources.

[Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) enables you to work
with the resources in your solution as a group. You can deploy, update, or delete all the resources
for your solution in a single, coordinated operation. You use a template for deployment and that
template can work for different environments such as testing, staging, and production. Resource
Manager provides security, auditing, and tagging features to help you manage your resources after
deployment.

Review the [Install](install-azurerm-ps.md) article to get Azure PowerShell up and running on your
system. Then read the [Get Started](get-started-azureps.md) article to begin using it. For information about the latest
release, see the [release notes](release-notes-azureps.md).

The following samples can help you learn how to perform common scenarios with Azure PowerShell:

* [Linux Virtual Machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json)
* [Windows Virtual Machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json)
* [Web Apps](https://docs.microsoft.com/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json)
* [SQL Databases](https://docs.microsoft.com/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json)


### Getting started with PowerShell

The Azure PowerShell cmdlets perform most of the same functions available in the Azure portal
interface. You should have a basic working knowledge Azure to be successful using the cmdlets. For
more information about Azure, consult the [Azure documentation](https://docs.microsoft.com/azure/).

You also need a working knowledge PowerShell. To get started with PowerShell, see
[Scripting with PowerShell](https://technet.microsoft.com/library/bb978526.aspx).

You can also watch this video:
[PowerShell Basics: (Part 1) Getting Started with PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).

To learn more about automating with Azure PowerShell, watch this video:
[Take Control of the Cloud with the Microsoft Azure PowerShell Cmdlets](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/WAD-B305#fbid=).

> [!NOTE]
> If you have deployments that use the classic deployment model that cannot be converted you can
install the Service Management version of Azure PowerShell. For more information, see
[Install the Azure PowerShell Service Management module](install-azure-ps.md).

## Other Azure PowerShell modules

### [Azure Active Directory](/azps-concepts/azuread)

Azure Active Directory PowerShell is the primary interface for managing Azure Active Directory.
These cmdlets provide capabilities to retrieve data from the directory, create new objects in the
directory, or change existing objects and configure the directory and its features.

There are two PowerShell modules. The newer AzureAD v2 module and the older MSOnline module. The
MSOnline module is used for functionality that is not yet available in the AzureAD module. If you
are developing new PowerShell scripts with Azure AD cmdlets you should use the newer AzureAD v2
cmdlets whenever possible. The older MSOnline module will be deprecated when all of the
functionality of that module has been migrated to the newer AzureAD module.

### [Azure Information Protection](/azps-concepts/azureinfoprotection)

The AIP PowerShell lets you administer the Azure Rights Management service. AIP PowerShell consists
of the following modules:

* AADRM

    These cmdlets let you administer the Azure Rights Management service. For more information
    about when you must use these PowerShell cmdlets and to see groupings of cmdlets by
    administration tasks, see
    [Administering Azure Rights Management by Using Windows PowerShell](/information-protection/deploy-use/administer-powershell).

* AzureInformationProtection

    The AIP cmdlets are installed with the [Azure Information Protection client](/information-protection/rms-client/aip-client).
    This module replaces the RMS Protection Tool and the AD RMS Bulk Protection Tool. These cmdlets
    can be used with the Azure Information Protection service, the Azure Rights Management service
    (Azure RMS), and Active Directory Rights Management Services (AD RMS).

### [Azure Service Fabric](/azps-concepts/servicefabric)

Service Fabric is a distributed systems platform that makes it easy to package, deploy, and manage
scalable and reliable microservices and addresses the significant challenges in developing and
managing cloud applications. The Service Fabric PowerShell module is installed with the
[Service Fabric SDK, runtime, and tools](/azure/service-fabric/service-fabric-get-started).

### [Azure ElasticDB](/azps-concepts/elasticdb)

Elastic Database Jobs enables you to reliably run a Transact-SQL (T-SQL) script or apply a
data-tier application package (DACPAC) across a group of Azure SQL databases. Using these cmdlets,
you can easily perform administrative operations such as schema changes, credentials management,
reference data updates, performance data collection, and tenant (customer) telemetry collection.

The ElasticDatabaseJobs module is in Preview status at this time. For more information, see
[Installing Elastic Database jobs overview](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-elastic-jobs-service-installation).
