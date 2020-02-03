---
title: Install Azure PowerShell with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/22/2019 
---

# Install the Azure PowerShell module

This article tells you how to install the Azure PowerShell modules using PowerShellGet. These instructions
work on Windows, macOS, and Linux platforms. For the Az module, currently no other installation methods
are supported.

## Requirements

Azure PowerShell works with PowerShell 5.1 or higher on Windows, or PowerShell Core 6.x and later on
all platforms. If you aren't sure if you have PowerShell, or are on macOS or Linux,
[install the latest version of PowerShell Core](/powershell/scripting/install/installing-powershell#powershell-core).

To check your PowerShell version, run the command:

```powershell-interactive
$PSVersionTable.PSVersion
```

To run Azure PowerShell in PowerShell 5.1 on Windows:

1. Update to [Windows PowerShell 5.1](/powershell/scripting/install/installing-windows-powershell#upgrading-existing-windows-powershell) if needed. If you're on Windows 10, you already
  have PowerShell 5.1 installed.
2. Install [.NET Framework 4.7.2 or later](/dotnet/framework/install).

There are no additional requirements for Azure PowerShell when using PowerShell Core.

## Install the Azure PowerShell module

> [!WARNING]
> You __can't__ have both the AzureRM and Az modules installed for PowerShell 5.1 for Windows at the same time. If you need to keep AzureRM available
> on your system, install the Az module for PowerShell Core 6.x or later. To do this,
> [install PowerShell Core 6.x or later](https://docs.microsoft.com/powershell/scripting/install/installing-powershell-core-on-windows) 
> and then follow these instructions in a PowerShell Core terminal.

The recommended install method is to only install for the active user:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

If you want to install for all users on a system, this requires administrator privileges. From an elevated PowerShell session either
run as administrator or with the `sudo` command on macOS or Linux:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope AllUsers
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

The Az module is a rollup module for the Azure PowerShell cmdlets. Installing it downloads all of
the available Azure Resource Manager modules, and makes their cmdlets available for use.

## Install offline

In some environments it's not possible to connect to the PowerShell Gallery. In those situations, you can still install offline using one of these methods:

* Download the modules to another location and use that as an installation source on your network. This
  can be a complicated process, but will let you cache PowerShell modules on a single server or file share
  to be deployed with PowerShellGet to any disconnected systems. Learn how to set up a local repository and
  install on disconnected systems with [Working with local PowerShellGet repositories](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
* [Download the Azure PowerShell MSI](install-az-ps-msi.md) to a machine connected to the network, and
  then copy the installer to systems without access to PowerShell Gallery. Keep in mind that the MSI
  installer only works for PowerShell 5.1 on Windows.
* Save the module with [Save-Module](/powershell/module/PowershellGet/Save-Module) to a file share, or
  save it to another source and manually copy it to other machines:
  
  ```powershell-interactive
  Save-Module -Name Az -Path '\\someshare\PowerShell\modules' -Force
  ```

## Troubleshooting

Here are some common problems seen when installing the Azure PowerShell module. If you experience a problem not listed here,
please [file an issue on GitHub](https://github.com/azure/azure-powershell/issues).

### Proxy blocks connection

If you get errors from `Install-Module` that indicate the PowerShell Gallery is unreachable, you may be behind
a proxy. Different operating systems will have different requirements for configuring a system-wide proxy, which
are not covered in detail here. Contact your system administrator for your proxy settings and how to configure
them for your OS.

PowerShell itself may not be configured to use this proxy automatically. With PowerShell 5.1 and later, configure
the proxy to use for a PowerShell session with the following command:

```powershell
(New-Object System.Net.WebClient).Proxy.Credentials = `
  [System.Net.CredentialCache]::DefaultNetworkCredentials
```

If your operating system credentials are configured correctly, this will route PowerShell requests through the proxy.
In order to have this setting persist between sessions, add the command to a
[PowerShell profile](/powershell/module/microsoft.powershell.core/about/about_profiles).

In order to install the package, your proxy needs to allow HTTPS connections to the following address:

* `https://www.powershellgallery.com`

## Sign in

To start working with Azure PowerShell, sign in with your Azure credentials.

```powershell-interactive
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

> [!NOTE]
>
> If you've disabled module autoloading, manually import the module with `Import-Module Az`. Because of
> the way the module is structured, this can take a few seconds.

You'll need to repeat these steps for every new PowerShell session you start. To learn how to persist your
Azure sign-in across PowerShell sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Update the Azure PowerShell module

If you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version. If you originally used the MSI package then you should download and install the new MSI in order to update. If you have any issues with updating using the package from PowershellGet then you will need to __reinstall__, rather than
just __update__. This is done in the same way as installing, but you may need to add the `-Force` argument:

```powershell
Install-Module -Name Az -AllowClobber -Force
```

Although this can overwrite installed modules, you may still have older versions left on your system.
To learn how to remove old versions of Azure PowerShell from your system, see [Uninstall the Azure PowerShell module](uninstall-az-ps.md).

## Use multiple versions of Azure PowerShell

It's possible to install more than one version of Azure PowerShell. To check if you have multiple versions of Azure PowerShell installed, use the following
command:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions | select Name,Version
```

To remove a version of Azure PowerShell, see [Uninstall the Azure PowerShell module](uninstall-az-ps.md).

You can install or load a specific version of the `Az` module by using the `-RequiredVersion` argument:

```powershell-interactive
# Install Az version 0.7.0
Install-Module -Name Az -RequiredVersion 0.7.0 
# Load Az version 0.7.0
Import-Module -Name Az -RequiredVersion 0.7.0
```

If you have more than one version of the module installed, module autoload and `Import-Module` load the
latest version by default.

## Provide feedback

If you find a bug in Azure Powershell, [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).
To provide feedback from the command line, use the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.

## Next Steps

To learn more about the Azure PowerShell modules and their features, see [Get Started with Azure PowerShell](get-started-azureps.md).
If you're familiar with Azure PowerShell and need to migrate from AzureRM, see [Migrate from AzureRM to Az](migrate-from-azurerm-to-az.md).
