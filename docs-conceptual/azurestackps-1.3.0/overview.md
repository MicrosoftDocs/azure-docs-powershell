---
title: Overview of Azure Stack Admin PowerShell | Microsoft Docs
description: An overview of Azure Stack Admin PowerShell with instructions for installation and configuration.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018
---
# Azure Stack Module 1.3.0

## Requirements:
Minimum supported Azure Stack version is 1804.

Note: If you are using an earlier version install version 1.2.11

## Known issues:

- Close Alert requires Azure Stack version 1803
- Some Storage cmdlets do require Azure Stack version 1804
- New-AzsOffer does not allow to create an offer with state public. The Set-AzsOffer cmdlet needs to be called afterwards to change the state.
- An IP Pool cannot be removed without a redeployment

## Breaking Changes
All breaking changes migrating from 1.2.11 are documented here https://aka.ms/azspowershellmigration

## Install
```
# Remove previous Versions
Uninstall-Module AzureRM.AzureStackAdmin -Force
Uninstall-Module AzureRM.AzureStackStorage -Force
Uninstall-Module -Name AzureStack -Force 


# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2017-03-09-profile -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.3.0
```
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
Preview release of the Azure Stack Compute administrator module which provides functionality to manage compute quotas, platform images, and virtual machine extensions.

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
