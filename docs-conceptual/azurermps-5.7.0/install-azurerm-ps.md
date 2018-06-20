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

To install Azure PowerShell, you need PowerShellGet version 1.1.2.0 or higher. To check if it is available
on your system, run the following command:

```powershell
Get-Module -Name PowerShellGet -ListAvailable | Select-Object -Property Name,Version,Path
```

You should see something similar to the following output:

```output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

If you need to update your installation of PowerShellGet, run the following command:

```powershell
Install-Module PowerShellGet -Force
```

If you don't have PowerShellGet installed, follow the instructions in the table below for your system.

|Scenario|Install instructions|
|---|---|
|Windows 10<br/>Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|Upgrade to PowerShell 5|<ol><li>[Install the latest version of WMF](https://www.microsoft.com/en-us/download/details.aspx?id=54616)</li><li>Run the following command:<br/>```Install-Module PowerShellGet -Force```</li></ol>|
|Windows with PowerShell 3 or PowerShell 4|<ol><il>[Get the PackageManagement modules](http://go.microsoft.com/fwlink/?LinkID=746217)</il><li>Run the following command:<br/>```Install-Module PowerShellGet -Force```</li></ol>|

> [!NOTE]
> Using PowerShellGet requires an Execution Policy that allows you to run scripts. For more
> information about PowerShell's Execution Policy, see
> [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

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
Import-Module -Name AzureRM -RequiredVersion 4.4.1
```

## Provide feedback

When using the Azure PowerShell, if you find any bugs, please [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). 
To provide feedback from the command line, use the `Send-Feedback` cmdlet.

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Get started with Azure PowerShell](get-started-azureps.md)