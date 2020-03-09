---
title: Overview of Azure Stack Admin PowerShell | Microsoft Docs
description: An overview of Azure Stack Admin PowerShell with instructions for installation and configuration.
author: sijuman 
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 03/09/2020
---
# Azure Stack Module 2.0.0

## Requirements:

Minimum supported Azure Stack version is 2002.

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](https://docs.microsoft.com/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## Install

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

Install-Module -Name Az.BootStrapper 

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzureAzProfile -Profile 2019-03-01-hybrid -Force 

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.0.0-preview -AllowPrerelease
```

## Release Notes

* Supported with 2002 update
* Changes include: