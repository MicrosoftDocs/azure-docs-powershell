---
title: Other ways to install  Azure PowerShell
description: How to install Azure PowerShell without PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/20/2018
---

# Install Azure PowerShell on Windows with MSI or Web Platform Installer

This article explains how to install Azure PowerShell on Windows using an MSI or Web Platform Installer (WebPI).  
Use these installation methods only if they're necessary for your system. The recommended way to install Azure PowerShell
on Windows is with PowerShellGet. For instructions on using PowerShellGet to install Azure PowerShell,
see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

To run Azure PowerShell in a Docker container, see [Run Azure PowerShell in Docker](azurerm-ps-in-docker.md).

To install on Linux or macOS environments, see [Install Azure PowerShell on macOS or Linux](install-azurermps-maclinux.md).

## Install or update on Windows using the MSI Package

Azure PowerShell can be installed using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/tag/v5.7.0-April2018). If you have installed previous
versions of Azure modules as an MSI, the installer automatically removes them. The MSI package installs
modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`.

When you install with the MSI, the `AzureRM` and `Azure` modules are pre-loaded into your PowerShell sessions.
To start working with Azure services, all you need to do is sign in with [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount).

```powershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Without setting up a context to persist credentials across sessions, you'll need to sign in for every new PowerShell session that is started. To learn about persisting your Azure credentials in PowerShell, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Install or update on Windows using the Web Platform Installer

Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install. If you have installed
previous versions of Azure modules from an MSI or with WebPI, the installer automatically removes them. Modules are
installed into `{$env:ProgramFiles}\WindowsPowerShell\Modules` but no version-specific folders are created.

When you install with the Web Platform Installer, the `AzureRM` and `Azure` modules are pre-loaded into your PowerShell sessions.
To start working with Azure services, all you need to do is sign in with [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount).

```powershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Without setting up a context to persist credentials across sessions, you'll need to sign in for every new PowerShell session that is started. To learn about persisting your Azure credentials in PowerShell, see [Persist user credentials across PowerShell sessions](context-persistence.md).