---
title: Overview of Azure Stack Hub Admin PowerShell 2.2.0 | Microsoft Docs
description: An overview of Azure Stack Hub Admin PowerShell with instructions for installation and configuration.
author: mattbriggs 
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 12/7/2021
---
# Azure Stack Hub Module 2.2.0

## Requirements:

Minimum supported Azure Stack Hub version is 2108.

Note: For earlier versions of Azure Stack check [Install Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## Install

For detailed install instructions please refer to [Install Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)
Run the following cmdlets from an elevated PowerShell session prompt:

```powershell  
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

Install-Module PowerShellGet -MinimumVersion 2.2.3 -Force
```

Close your PowerShell session, then open a new PowerShell session so that update can take effect. 
Run the following command from a PowerShell session:

```powershell  
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Install-Module -Name Az.BootStrapper -Force

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzProfile -Profile 2020-09-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.2.0 -AllowPrerelease
```


## Release Notes

* Supported with 2108 update.  

  Please refer to https://github.com/Azure/azurestack-powershell/releases/tag/v2.2.0 forr detailed release notes
