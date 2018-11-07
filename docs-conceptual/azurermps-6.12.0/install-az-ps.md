---
title: Install Azure PowerShell with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/29/2018
---

# Install Azure PowerShell with PowerShellGet

This article tells you how to install the Azure PowerShell modules using PowerShellGet. For the preview release of Az, no other install methods are supported. 

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
> You shouldn't have both the `AzureRM` and `Az` modules installed on a system at the same time. In order to install
> the `Az` module, `AzureRM` must be uninstalled. For instructions on how to do that, see
> [Uninstall the Azure PowerShell module (AzureRM)](uninstall-azurerm-ps.md).

To install modules at a global scope, you need elevated privileges to install modules from the PowerShell Gallery. To install Azure PowerShell, run the following command in an elevated session ("Run as Administrator" on Windows, or with superuser privileges on macOS or Linux):

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

To start working with Azure PowerShell, you need to load `Az` into your current PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in
with your Azure credentials.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module Az
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `Az` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
To learn how to persist your Azure sign-in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

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

You can load a specific version of the `Az` module by using the `-RequiredVersion` argument with `Install-Module` or `Import-Module`:

```powershell-interactive
Install-Module -Name Az -RequiredVersion 0.4.0
Import-Module -Name Az -RequiredVersion 0.4.0
```

If you have more than one version of the module installed, the latest version is loaded by default when importing.

## Provide feedback

If you find a bug when using Azure Powershell, [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).
To provide feedback from the command line, use the [Send-Feedback](/powershell/module/az.profile/send-feedback) cmdlet.

## Next Steps

To get started using Azure PowerShell, see [Get Started with Azure PowerShell](get-started-azureps.md) to learn more about the module and its features.