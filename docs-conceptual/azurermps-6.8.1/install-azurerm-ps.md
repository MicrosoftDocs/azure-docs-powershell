---
title: Install Azure PowerShell on Windows with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/11/2018
---

# Install Azure PowerShell on Windows with PowerShellGet

This article explains the steps to install the Azure PowerShell modules in a Windows environment using
PowerShellGet. PowerShellGet and module management is the preferred way to install Azure PowerShell but if you would rather install with
the Web Platform Installer or MSI package, see [Other installation methods](other-install.md).

For instructions to install Azure PowerShell on other platforms, see [Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).

The Azure classic deployment model is not supported by this version of Azure PowerShell. For support for classic deployments,
follow the instructions in [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).

## Requirements

Starting with Azure PowerShell version 6.0, Azure PowerShell requires PowerShell version 5.0. To check the version of PowerShell running
on your machine, run the following command:

```powershell
$PSVersionTable.PSVersion
```

If you have an outdated version, see [Upgrading existing Windows PowerShell](/powershell/scripting/setup/installing-windows-powershell?view=powershell-6#upgrading-existing-windows-powershell).

> [!IMPORTANT]
> The module described in this document, AzureRM, uses .NET Framework. This makes it incompatible with PowerShell 6.0,
> which uses .NET Core. If you are using PowerShell 6.0, follow the [installation instructions for
> macOS and Linux](install-azurermps-maclinux.md).

## Install the Azure PowerShell module

You need elevated privileges to install modules from the PowerShell Gallery. To install Azure PowerShell,
run the following command in an elevated session:

```powershell
Install-Module -Name AzureRM
```

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install
> the latest version of NuGet.

By default, the PowerShell gallery isn't configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer `Yes` or `Yes to All` to continue with the installation.

The `AzureRM` module is a rollup module for the Azure PowerShell cmdlets. Installing it downloads all of
the available Azure Resource Manager modules, and makes their cmdlets available for use.

## Sign in

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

## Update the Azure PowerShell module

You can update your Azure PowerShell installation by running [Update-Module](/powershell/module/powershellget/update-module). This command does __not__ uninstall earlier versions.

```powershell
Update-Module -Name AzureRM
```

If you want to remove older versions of Azure PowerShell from your system, see [Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

## Use multiple versions of Azure PowerShell

It's possible to install more than one version of Azure PowerShell. You might need more than one version if you work with on-premises Azure Stack resources,
run an older version of Windows, or use the Azure classic deployment model. To install an older version, provide the
`-RequiredVersion` argument when installing.

```powershell
# Install version 1.2.9 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

When loading the Azure PowerShell module the latest version is loaded by default. To load a different version, provide the `-RequiredVersion` argument.

```powershell
# Load version 1.2.9 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 1.2.9
```

## Provide feedback

If you find a bug when using Azure Powershell, [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).
To provide feedback from the command line, use the [Send-Feedback](/powershell/module/azurerm.profile/send-feedback) cmdlet.

## Next Steps

To get started using Azure PowerShell, see [Get Started with Azure PowerShell](get-started-azureps.md) to learn more about the module and its features.