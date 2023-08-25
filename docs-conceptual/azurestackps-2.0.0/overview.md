---
title: Overview of Azure Stack Hub Admin PowerShell | Microsoft Docs
description: An overview of Azure Stack Hub Admin PowerShell with instructions for installation and configuration.
author: mattbriggs 
ms.author: jgerend
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 09/23/2021
---
# Azure Stack Hub Module 2.0.0

## Requirements:

Minimum supported Azure Stack Hub version is 2002.

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## Install

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

Install-Module -Name Az.BootStrapper -Force -AllowPrerelease

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.0.0-preview -AllowPrerelease
```


## Release Notes

* Supported with 2002 update.  

  The Azure Stack Hub 2.0.0 is a breaking change. The module uses the Az module rather than the AzureRM module. You can find a migration guide and a list of breaking changes in [Migrate from AzureRM to Azure PowerShell Az in Azure Stack Hub](/azure-stack/operator/azure-stack-powershell-install).