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

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## Install

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Install-Module -Name AzureRM -RequiredVersion 2.5.0

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.7.2
```

## Release Notes

* Supported with 1904 update
* This a breaking change release. For details on the breaking changes, refer to <https://aka.ms/azspshmigration170>
* Breaking change: Backup changes to cert-based encryption mode. Support for symmetric keys is deprecated.
* For details on the breaking changes, refer to https://aka.ms/azspshmigration170
* Azs.Storage.Admin Module 
* Bug fix - New Storage Quota uses defaults if none provided.