---
title: Install Azure PowerShell on Windows with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/16/2018
---

# Install Azure PowerShell on Windows with PowerShellGet

[!INCLUDE [migrate-to-az](../includes/migrate-to-az.md)]

This article explains the steps to install the Azure PowerShell modules for PowerShell 5.x for
Windows using PowerShellGet. PowerShellGet and module management is the preferred way to install
Azure PowerShell but if you would rather install with the Web Platform Installer or MSI package, see
[Other installation methods](other-install.md).

The Azure classic deployment model is not supported by this version of Azure PowerShell. For support
for classic deployments, follow the instructions in
[Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> The AzureRM module is not supported for macOS or Linux. To use Azure PowerShell cmdlets on these
> platforms, [Install the Az module](/powershell/azure/install-az-ps).

## Requirements

Starting with Azure PowerShell version 6.0, Azure PowerShell requires PowerShell version 5.0. To
check the version of PowerShell running on your machine, run the following command:

```powershell-interactive
$PSVersionTable.PSVersion
```

If you have an outdated version, see
[Upgrading existing Windows PowerShell](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).

> [!IMPORTANT]
> The module described in this document, AzureRM, uses .NET Framework. This makes it incompatible
> with PowerShell 6.0, which uses .NET Core. If you are using PowerShell 6.0, follow the
> [installation instructions for macOS and Linux](/powershell/azure/install-az-ps).

## Install the Azure PowerShell module

You need elevated privileges to install modules from the PowerShell Gallery. To install Azure
PowerShell, run the following command in an elevated session:

```azurepowershell-interactive
Install-Module -Name AzureRM -AllowClobber
```

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the
> latest version of NuGet.

By default, the PowerShell gallery isn't configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer `Yes` or `Yes to All` to continue with the installation.

The `AzureRM` module is a rollup module for the Azure PowerShell cmdlets. Installing it downloads
all of the available Azure Resource Manager modules, and makes their cmdlets available for use.

## Sign in

To start working with Azure PowerShell, sign in with your Azure credentials.

```azurepowershell-interactive
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> If you've disabled module autoloading, you need to manually import the module with
> `Import-Module AzureRM`. Because of the way the module is structured, this can take a few seconds.

You'll need to repeat these steps for every new PowerShell session you start. To learn how to
persist your Azure sign-in across PowerShell sessions, see
[Persist user credentials across PowerShell sessions](context-persistence.md).

## Update the Azure PowerShell module

You can update your Azure PowerShell installation by running
[Update-Module](/powershell/module/powershellget/update-module). This command does **not** uninstall
earlier versions.

```powershell-interactive
Update-Module -Name AzureRM
```

If you want to remove older versions of Azure PowerShell from your system, see
[Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

## Use multiple versions of Azure PowerShell

It's possible to install more than one version of Azure PowerShell. To check if you have multiple
versions of Azure PowerShell installed, use the following command:

```azurepowershell-interactive
Get-InstalledModule -Name AzureRM -AllVersions | select Name,Version
```

To remove a version of Azure PowerShell, see
[Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

You might need more than one version if you work with on-premises Azure Stack resources, run an
older version of Windows, or use the Azure classic deployment model. To install an older version,
provide the `-RequiredVersion` argument when installing.

```azurepowershell-interactive
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

When loading the Azure PowerShell module the latest version is loaded by default. To load a
different version, provide the `-RequiredVersion` argument.

```azurepowershell-interactive
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## Provide feedback

If you find a bug when using Azure Powershell,
[file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). To provide feedback
from the command line, use the [Send-Feedback](/powershell/module/azurerm.profile/send-feedback)
cmdlet.

## Next Steps

To get started using Azure PowerShell, see
[Get Started with Azure PowerShell](get-started-azureps.md) to learn more about the module and its
features.
