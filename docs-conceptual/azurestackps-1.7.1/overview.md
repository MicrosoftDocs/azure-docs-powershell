---
title: Overview of Azure Stack Admin PowerShell | Microsoft Docs
description: An overview of Azure Stack Admin PowerShell with instructions for installation and configuration.
author: sijuman 
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 02/06/2019
---
# Azure Stack Module 1.7.2

## Requirements:

Minimum supported Azure Stack version is 1904.

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## Install PowerShell for Azure Stack

Installation has three steps:

1. Install Azure Stack PowerShell depending on your version of Azure Stack
2. Enable additional storage features
3. Confirm the installation of PowerShell

### Install Azure Stack PowerShell

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install the AzureRM.BootStrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRM.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Get-AzureRmProfile -Update
Use-AzureRmProfile -Profile 2019-03-01-hybrid -Force
Install-Module -Name AzureStack -RequiredVersion 1.7.2
```

### Enable additional storage features

```
# Install the Azure.Storage module version 4.5.0
Install-Module -Name Azure.Storage -RequiredVersion 4.5.0 -Force -AllowClobber

# Install the AzureRm.Storage module version 5.0.4
Install-Module -Name AzureRM.Storage -RequiredVersion 5.0.4 -Force -AllowClobber

# Remove incompatible storage module installed by AzureRM.Storage
Uninstall-Module Azure.Storage -RequiredVersion 4.6.1 -Force

# Load the modules explicitly specifying the versions
Import-Module -Name Azure.Storage -RequiredVersion 4.5.0
Import-Module -Name AzureRM.Storage -RequiredVersion 5.0.4
```

## Release Notes

* Supported with 1904 update
* This a breaking change release. For details on the breaking changes, refer to <https://aka.ms/azspshmigration170>
* Azs.Backup.Admin Module
        * Breaking change: Backup changes to cert-based encryption mode. Support for symmetric keys is deprecated.
* Azs.Fabric.Admin Module
        * Deprecation
            * Get-AzsInfrastructureVolume has been deprecated, we provide new cmdlet Get-AzsVolume
            * Get-AzsStorageSystem has been deprecated, we provide new cmdlet Get-AzsStorageSubSystem
            * Get-AzsStoragePool has been deprecated, the StorageSubSystem object has the capacity property
* Azs.Compute.Admin Module
            * BugFix: Add-AzsPlatformImage, Get-AzsPlatformImage : Calling ConvertTo-PlatformImageObject only in the success path
            * BugFix: Add-AzsVmExtension, Get-AzsVmExtension : Calling ConvertTo-VmExtensionObject only in the success path
* Azs.Storage.Admin Module
            * Bug fix - New Storage Quota uses defaults if none provided.'
