---
title: Install Azure PowerShell on Windows with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/15/2018
---

# Install Azure PowerShell on Windows with PowerShellGet

This article explains the steps to install the Azure PowerShell modules in a Windows environment using
PowerShellGet.  This is the preferred way to install Azure PowerShell, but if you would rather install with
the Web Platform Installer or MSI package, see [Other installation methods](other-install.md).

For instructions to install Azure PowerShell on other platforms, see [Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).

The Azure classic deployment model is not supported by this version of Azure PowerShell. For support for classic deployments,
follow the instructions in [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).

## Requirements

Azure PowerShell version 6.1.0 requires version 5.0 (or higher) of PowerShell. To check the version of PowerShell running
on your machine, use the following command:

```powershell
$PSVersionTable.PSVersion
```

If you have an outdated version, see [Upgrading existing Windows PowerShell](/powershell/scripting/setup/installing-windows-powershell?view=powershell-6#upgrading-existing-windows-powershell).

## Install the Azure PowerShell module

Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges. Run the
following command from an elevated PowerShell session:

```powershell
Install-Module -Name AzureRM 
```

> [!IMPORTANT]
> This command will __not__ remove any existing installations of the Azure PowerShell module on
> your system. To remove old installations see [Uninstall the Azure PowerShell module](#uninstall-the-azure-powershell-module).

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install
> the latest version of NuGet.

By default, the PowerShell gallery is not configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer 'Yes' or 'Yes to All' to continue with the installation.

The AzureRM module is a rollup module for the Azure Resource Manager cmdlets, and downloads and
installs all of the available cmdlets for working with Azure.

To start working with the Azure PowerShell module, you need to load it into your current PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then log in
with your Azure credentials.

```powershell
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for login
Connect-AzureRmAccount
```

To learn about persisting your sign in credentials across sessions, see [Persist user logins across PowerShell sessions](context-persistence.md).

## Uninstall the Azure PowerShell module

To uninstall the Azure PowerShell module, use the [Uninstall-Module](/powershell/module/powershellget/uninstall-module) cmdlet. To uninstall 
the most recent version of the Azure PowerShell on your system:

```powershell
Uninstall-Module -Name AzureRM
```

You can also delete a single version:

```powershell
Uninstall-Module -Name AzureRM -RequiredVersion 6.1.0
```

Or completely remove Azure PowerShell from your system.

```powershell
Uninstall-Module -Name AzureRM -AllVersions
```

To uninstall all versions of Azure PowerShell except for the latest, run the following
command:

```powershell
Get-InstalledModule -Name AzureRM -AllVersions |
    Where-Object -Property Version -ne $(Get-InstalledModule -Name AzureRM).Version |
    ForEach-Object {Uninstall-Module -Name $_.Name -RequiredVersion $_.Version}
```

## Update the Azure PowerShell module

You can update your Azure PowerShell installation by running [Update-Module](/powershell/module/powershellget/update-module) to pull the latest available version. This does __not__ uninstall earlier versions.

```powershell
Update-Module -Name AzureRM
```

If you do not want to keep earlier versions, you can run the following command to remove all _but_ the latest version of Azure PowerShell:

```powershell
Get-InstalledModule -Name AzureRM -AllVersions |
    Where-Object -Property Version -ne $(Get-InstalledModule -Name AzureRM).Version |
    ForEach-Object {Uninstall-Module -Name $_.Name -RequiredVersion $_.Version}
```

## Use multiple versions of Azure PowerShell

If you need multiple versions of Azure PowerShell installed on your system, this is possible to do. When upgrading to a new version, take care to *not* delete
any versions that you still need on your machine, by using only `Uninstall-Module` with the `-RequiredVersion` argument. When loading the Azure PowerShell
module, the latest version is loaded by default, so if you require a different version then use the `-RequiredVersion` argument.

```powershell
# Import an earlier version of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 5.7.0
```

## Provide feedback

When using the Azure PowerShell, if you find any bugs, please [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). 
To provide feedback from the command line, use the `Send-Feedback` cmdlet.

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Get started with Azure PowerShell](get-started-azureps.md)