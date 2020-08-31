---
title: Other ways to install  Azure PowerShell
description: How to install Azure PowerShell without PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/20/2018 
ms.custom: devx-track-azurepowershell
---
# Install Azure PowerShell on Windows with MSI or Web Platform Installer

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

This article explains how to install Azure PowerShell on Windows using an MSI or Web Platform Installer (WebPI).
Use these installation methods only if they're necessary for your system. The recommended way to install Azure PowerShell
on Windows is with PowerShellGet. For instructions on using PowerShellGet to install Azure PowerShell,
see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

## Install or update on Windows using the MSI Package

Azure PowerShell can be installed using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/tag/v5.7.0-April2018). If you have installed previous
versions of Azure modules as an MSI, the installer automatically removes them. The MSI package installs
modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`. Both the `AzureRM` and `Azure` modules are installed.

> [!NOTE]
> Only use the `Azure` module if you are working with the Azure classic deployment model.

To start working with Azure PowerShell, you need to load `AzureRM` into your current PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in
with your Azure credentials.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `AzureRM` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
To learn how to persist your Azure sign in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Install or update on Windows using the Web Platform Installer

Download the [Azure PowerShell WebPI package](https://aka.ms/webpi-azps) and start the install. If you have installed
previous versions of Azure modules from an MSI or with WebPI, the installer automatically removes them. Modules are
installed into `${env:ProgramFiles}\WindowsPowerShell\Modules`. Both the `AzureRM` and `Azure` modules are installed.

> [!NOTE]
> Only use the `Azure` module if you are working with the Azure classic deployment model.

To start working with Azure PowerShell, you need to load `AzureRM` into your current PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in
with your Azure credentials.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `AzureRM` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
To learn how to persist your Azure sign in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).
