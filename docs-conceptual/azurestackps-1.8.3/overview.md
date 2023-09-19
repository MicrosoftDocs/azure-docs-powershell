---
title: Overview of Azure Stack Admin PowerShell | Microsoft Docs
description: An overview of Azure Stack Admin PowerShell with instructions for installation and configuration.
author: mattbriggs 
ms.author: jgerend
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 09/23/2021
---
# Azure Stack Module 1.8.3

## Requirements:

Minimum supported Azure Stack version is 2002.

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

> [!IMPORTANT]  
> You've reached a webpage for an outdated version of Azure Stack Hub PowerShell. All versions of the Azure Resource Manager (AzureRM) PowerShell module are outdated, but not out of support. AzureRM modules will no longer be updated in future Azure Stack Hub builds. Az modules will be used for builds 2002 and later. The 2020-09-01-hybrid profile is not supported for AzureRM modules.  
> 
> The Az PowerShell module is now the recommended PowerShell module for interacting with Azure and Azure Stack Hub. To get started with the Az PowerShell module, see [Install PowerShell Az preview module for Azure Stack Hub](/azure-stack/operator/powershell-install-az-module). To learn how to migrate to the Az PowerShell module. see [Migrate from AzureRM to Azure PowerShell Az in Azure Stack Hub](/azure-stack/operator/migrate-azurerm-az). For details on the increased functionality of the Az modules, which have been adopted across global Azure, see [Introducing the Azure Az PowerShell module](/powershell/azure/new-azureps-module-az).

## Install

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.8.3
```

## Release Notes

* Supported with 1910 update
