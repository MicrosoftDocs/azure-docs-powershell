---
title: Other ways to install Azure PowerShell
description: How to install Azure PowerShell without PowerShellGet using an MSI
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/11/2018
---

# Install Azure PowerShell on Windows with MSI

This article explains how to install Azure PowerShell on Windows using an MSI installer.  
Use these installation methods only if they're necessary for your system. The recommended way to install Azure PowerShell
on Windows is with PowerShellGet. For instructions on using PowerShellGet to install Azure PowerShell,
see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

> [!NOTE]
> The Web Platform Installer method of installation is no longer available for versions of Azure PowerShell 6.x
> and higher. If you require use of the Web Platform Installer please consider using the MSI instead, or you can
> install an earlier version of Azure PowerShell.

To run Azure PowerShell in a Docker container, see [Run Azure PowerShell in Docker](azurerm-ps-in-docker.md).

To install on Linux or macOS environments, see [Install Azure PowerShell on macOS or Linux](install-azurermps-maclinux.md).

## Install or update on Windows using the MSI Package

Azure PowerShell can be installed using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/latest). If you have installed previous
versions of Azure modules as an MSI, the installer automatically removes them. The MSI package installs
modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`. Both the `AzureRM` and `Azure` modules are installed.

> [!NOTE]
> Only use the `Azure` module if you are working with the Azure classic deployment model.

To start working with Azure PowerShell, you need to load `AzureRM` into your current PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in
with your Azure credentials.

```powershell
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `AzureRM` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
To learn how to persist your Azure sign-in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).