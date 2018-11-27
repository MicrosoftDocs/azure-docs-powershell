---
title: Install Azure PowerShell 'Az' with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet on Windows, macOS, and Linux.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/26/2018
---

# Install the Azure PowerShell 'Az' module

This article tells you how to install the Azure PowerShell modules using PowerShellGet. These instructions work on Windows, macOS, and Linux
platforms. For the preview release of Az, no other install methods are supported. 

## Requirements

Azure PowerShell works with either PowerShell 5.x on Windows, or PowerShell 6.x on any platform. To check the version of PowerShell running
on your machine, run the following command:

```powershell-interactive
$PSVersionTable.PSVersion
```

If you have an outdated version or need to install PowerShell, see [Installing various versions of PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/setup/installing-powershell?view=powershell-6). Install
information for your platform is linked from that page.

## Install the Azure PowerShell module

> [!IMPORTANT]
>
> You can have both the `AzureRM` and `Az` modules installed at the same time. If you have both modules installed, __don't enable aliases__.
> Enabling aliases will cause conflicts between `AzureRM` cmdlets and `Az` command aliases, and could cause unexpected behavior.
> It's recommended that before installing the `Az` module, you uninstall `AzureRM`. You can always uninstall `AzureRM` or enable aliases
> at any time. For uninstall instructions, see [Uninstall the Azure PowerShell module (AzureRM)](uninstall-azurerm-ps.md). 

To install modules at a global scope, you need elevated privileges to install modules from the PowerShell Gallery. To install Azure PowerShell,
run the following command in an elevated session ("Run as Administrator" on Windows, or with superuser privileges on macOS or Linux):

```powershell-interactive
Install-Module -Name Az -AllowClobber
```

If you don't have access to administrator privileges, you can install for the current user by adding the `-Scope` argument.

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

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

The `Az` module is a rollup module for the Azure PowerShell cmdlets. Installing it downloads all of
the available Azure Resource Manager modules, and makes their cmdlets available for use.

## Sign in

To start working with Azure PowerShell, sign in with your Azure credentials.

```powershell-interactive
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

> [!NOTE]
>
> If you've disabled module autoloading, you need to manually import the module with `Import-Module Az`. Because of
> the way the module is structured, this can take a few seconds.

You'll need to repeat these steps for every new PowerShell session you start. To learn how to persist your Azure sign-in
across PowerShell sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Update the Azure PowerShell module

You can update your Azure PowerShell installation by running [Update-Module](/powershell/module/powershellget/update-module). This command does __not__ uninstall earlier versions.

```powershell-interactive
Update-Module -Name Az
```

If you want to remove older versions of Azure PowerShell from your system, see [Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

## Use multiple versions of Azure PowerShell

It's possible to install more than one version of Azure PowerShell. To check if you have multiple versions of Azure PowerShell installed, use the following
command:

```powershell-interactive
Get-Module -Name Az -List | select Name,Version
```

To remove a version of Azure PowerShell, see [Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

You can load a specific version of the `Az` module by using the `-RequiredVersion` argument with `Install-Module` and `Import-Module`:

```powershell-interactive
Install-Module -Name Az -RequiredVersion 0.4.0
Import-Module -Name Az -RequiredVersion 0.4.0
```

If you have more than one version of the module installed, the latest version is loaded by default.

## Provide feedback

If you find a bug when using Azure Powershell, [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).
To provide feedback from the command line, use the [Send-Feedback](/powershell/module/az.profile/send-feedback) cmdlet.

## Next Steps

To get started using Azure PowerShell, see [Get Started with Azure PowerShell](get-started-azureps.md) to learn more about the module and its features.
