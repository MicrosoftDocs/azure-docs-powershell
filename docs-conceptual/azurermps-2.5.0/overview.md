---
title: Overview of Azure Stack PowerShell | Microsoft Docs
description: An overview of Azure Stack PowerShell with instructions for installation and configuration.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018 
ms.custom: devx-track-azurepowershell
---
# AzureRM Module 2.5.0

## Requirements:
Minimum supported Azure Stack version is 1904.

Note: If you are using an earlier version install version 1.2.11


## Install
```powershell-interactive
# Remove previous versions of AzureStack modules
Uninstall-Module -Name AzureStack -Force 
Uninstall-Module -Name AzureRM -Force 
Uninstall-Module AzureRM.AzureStackAdmin -Force -ErrorAction Continue
Uninstall-Module AzureRM.AzureStackStorage -Force -ErrorAction Continue
Get-Module Azs.* -ListAvailable | Uninstall-Module -Force
Get-Module Azure.* -ListAvailable | Uninstall-Module -Force


# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2018-03-01-hybrid -Force

```

## Release Notes
* AzureRm.Resources
    * New Resources module supporting 2018-05-01 api version with 2019-03-01-hybrid profile
    * PolicyDefinition(2016-12-01) and PolicyAssisgment(2017-06-01-preview) operations are still with old api versions
* AzureRm.Compute
    * New compute module supporting 2017-12-01 api version.'


* This release corresponds to the azurestack specific api profile 2019-03-01-hybrid
* All the modules are taking greater than or equal to dependency on the AzureRm.Profile module.
* Api version suppoerted by  each of the modules are updated. 
    * Compute - 2017-12-30
    * Network - 2017-10-01
    * Storage - 2016-01-01
    * Resources - 2018-02-01
    * Keyvault - 2016-10-01
    * Dns - 2016-04-01
* The complete api version map for each of the resource types can be found at https://github.com/Azure/azure-rest-api-specs/blob/master/profile/2018-03-01-hybrid.json

## Content:
### Azure Bridge
Preview release of the Azure Stack AzureBridge administrator module which allows you to syndicate images from Azure.

### Backup
Preview release of the Backup administrator module that allows administrators to:
- Configure where backups are stored
- Perform backups
- List and restore completed backup

### Commerce
Preview release of the Azure Stack Commerce administrator module which provides a way to view aggregate data usage across your Azure Stack system.

### Compute
Preview release of the Azure Stack Compute administrator module which provides functionality to manage compute quotas, platform images, managed disks and virtual machine extensions.

### Fabric
Preview release of the Azure Stack Fabric administrator module which allows administrators to view and manage infrastructure components:
- Stop, Start and Shutdown of scale unit nodes
- Drain and Resume of scale unit nodes for FRU related activities
- Repair of scale unit nodes
- Restart of Infrastructure role
- Stop, Start and Shutdown of Infrastructure role instances
- Create new IP Pools


### Gallery
Preview release of the Azure Stack Gallery administrator module which provides functionality to manage gallery items in the Azure Stack marketplace.

### Infrastructure Insights
Preview release of the Infrastructure Insights administrator module which allows administrators:
- View the health of their Azure Stack stamp resources
- View and manage alerts

### KeyVault
Preview release of the Azure Stack KeyVault administrator module which allows administrator to view KeyVault quotas.

### Network
Preview release of the Network administrator module which allows:
- Management of network quotas
- View allocated network resources such as public IP addresses, virtual networks, load balancers
- Provides a cmdlet which displays an administrator overview

### Storage
Preview release of the Azure Stack Storage administrator module.  In this release we provide the functionality to:
- Manage storage quotas
- Garbage collect deleted storage resources
- Restore deleted storage accounts
- Migrate containers from one share to another
- View information about the individual storage components
- View usage and performance information

### Subscription Admin
Preview release of the Azure Stack Subscription administrator module.  This module provides functionality for administrators to:
- Manage plans and offers
- View usage and performance information
- Manage RBAC

### Subscription
Preview release of the Azure Stack Subscription module.  This module provides functionality for Users to:
- Create, Delete and Update Subscriptions

### Update
Preview release of the Azure Stack Update administrator module.  In this module administrators can:
- List and install available updates
- Resume interrupted updates
- View installed updates
