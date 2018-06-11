---
title: Install Azure PowerShell with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/31/2018
---

# Install Azure PowerShell with PowerShellGet

This article explains the steps to install the Azure PowerShell modules in a Windows environment using
PowerShellGet.  This is the preferred way to install Azure PowerShell, but if you would rather install with
the Web Platform Installer or MSI package, see [Other installation methods](other-install.md).

If you want to use Azure PowerShell on macOS or Linux, see the following article:
[Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).

## System requirements

Azure PowerShell version 6.1.0 requires version 5.0 (or higher) of PowerShell. For information on
upgrading to PowerShell 5.0, see
[Upgrading existing Windows PowerShell](/powershell/scripting/setup/installing-windows-powershell?view=powershell-6#upgrading-existing-windows-powershell).

PowerShellGet is automatically included as part of PowerShell 5.0.

## Install or update the Azure PowerShell module

Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges. Run the
following command from an elevated PowerShell session:

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

> [!IMPORTANT]
> This command will update any existing installation of Azure PowerShell on your system. If you need to have more than
> one version installed, see the FAQ answer for [Can I install multiple versions of Azure PowerShell?](#multiple-versions)

By default, the PowerShell gallery is not configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer 'Yes' or 'Yes to All' to continue with the installation.

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install
> the latest version of NuGet.

The AzureRM module is a rollup module for the Azure Resource Manager cmdlets. When you install the
AzureRM module, any Azure PowerShell module not previously installed is downloaded from the
PowerShell Gallery.

## Load the Azure PowerShell module

Once the module is installed, you need to load the module into your PowerShell session. You should
do this in a normal (non-elevated) PowerShell session. Modules are loaded using the `Import-Module`
cmdlet, as follows:

```powershell
Import-Module -Name AzureRM
```

## Reporting issues and feedback

If you encounter any bugs with the tool, please [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). 
To provide feedback from the command line, use the `Send-Feedback` cmdlet.

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Get started with Azure PowerShell](get-started-azureps.md)

## Frequently asked questions

### <a id="helpmechoose"></a>How do I check the version of Azure PowerShell?

Although we encourage you to upgrade to the latest version as early as possible, several versions
of Azure PowerShell are supported. To determine the version of Azure PowerShell you have installed,
run `Get-Module AzureRM` from your command line.

```powershell
Get-Module AzureRM -ListAvailable | Select-Object -Property Name,Version,Path
```

### Can I use Azure PowerShell for Azure Classic deployments?

If you have deployments that use the classic deployment model you can install the Service
Management version of Azure PowerShell. For more information, see [Install the Azure PowerShell
Service Management module](/powershell/azure/servicemanagement/install-azure-ps). The Azure and AzureRM modules share
common dependencies. If you use both the Azure and AzureRM modules, you should install the same
version of each package.

### <a name="multiple-versions"/>Can I install multiple versions of Azure PowerShell?

PowerShellGet the only method of installation that supports multiple versions. To install multiple versions,
you can add the `-RequiredVersion` parameter to the `Install-Module` cmdlet. For example, to install both
versions 6.1.0 and 1.2.9:

```powershell
Install-Module -Name AzureRM -RequiredVersion 6.1.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

Only one version of the module can be loaded in a PowerShell session. You must open a new
PowerShell window and use `Import-Module` to import a specific version of the Azure PowerShell module.

```powershell
Import-Module -Name AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used
side by side. When loading an earlier version of the Azure PowerShell, incompatible versions of the
**AzureRM.Profile** module are loaded. This results in the cmdlets prompting you to log in whenever
you execute a cmdlet.
