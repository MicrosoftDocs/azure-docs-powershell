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
# Azure Stack Module 1.6.0

## Requirements:
Minimum supported Azure Stack version is 1811.

Note: If you are using an earlier version install version 1.6.0

## Install
```
# Remove previous versions of AzureStack and AzureRM modules
Uninstall-Module -Name AzureRM -Force
Uninstall-Module -Name Azure.Storage -Force
Uninstall-Module -Name AzureStack -Force
Get-Module -Name "Azs*" -ListAvailable | Uninstall-Module  -Force 
Get-Module -Name "AzureRm*" -ListAvailable | Uninstall-Module  -Force

# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2018-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.6.0
```

## Release Notes
* Supported with 1811 update
* Azs.Compute.Admin Module
    * Fixed missing Azs prefix for New-DataDiskObject and added alias with warning of future deprecation.
* Azs.Update.Admin Module
    * Added a warning to recommend running Test-AzureStack before Install-AzsUpdate
* Azs.Fabric.Admin
    * New cmdlet (The features are supported by Azure Stack 1811+)
        * Get-AzsDrive
        * Get-AzsVolume
        * Get-AzsStorageSubSystem
    * Deprecation
        * Get-AzsInfrastructureVolume is an alias now to the cmdlet Get-AzsVolume
* Azs.InfrastructureInsights.Admin
    *  Added a new cmdlet Repair-AzsAlert
* Azs.Storage.Admin
    * Bug fix where default quota values are not being used
* Azs.Subscriptions.Admin Module
    * Fixed missing Azs prefix for New-AddonPlanDefinitionObject and added alias with warning of future deprecation.
