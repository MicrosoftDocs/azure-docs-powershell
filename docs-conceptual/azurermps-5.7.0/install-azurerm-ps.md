---
title: Install Azure PowerShell on Windows with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/15/2018
---

# Install Azure PowerShell on Windows with PowerShellGet

[!INCLUDE [migrate-to-az](../includes/migrate-to-az.md)]

This article explains the steps to install the Azure PowerShell modules for PowerShell 5.x for Windows using
PowerShellGet. PowerShellGet and module management is the preferred way to install Azure PowerShell but if you would rather install with
the Web Platform Installer or MSI package, see [Other installation methods](other-install.md).

The Azure classic deployment model is not supported by this version of Azure PowerShell. For support for classic deployments,
follow the instructions in [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> The AzureRM module is not supported for macOS or Linux. To use Azure PowerShell cmdlets on these platforms,
> [Install the Az module](/powershell/azure/install-az-ps).

## Requirements

To install Azure PowerShell, you need PowerShellGet version 1.1.2.0 or higher. To check if it is available
on your system, run the following command:

```powershell-interactive
Get-InstalledModule -Name PowerShellGet -AllVersions | Select-Object -Property Name,Version,Path
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

```powershell-interactive
Install-Module PowerShellGet -Force
```

If you don't have PowerShellGet installed, follow the instructions in the table below for your system.

|Scenario|Install instructions|
|---|---|
|Windows 10<br/>Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|Upgrade to PowerShell 5| <ol><li>[Install the latest version of WMF](https://www.microsoft.com/download/details.aspx?id=54616)</li><li>Run the following command:<br/>```Install-Module PowerShellGet -Force```</li></ol>|
|Windows with PowerShell 3 or PowerShell 4|<ol><il>[Get the PackageManagement modules](https://go.microsoft.com/fwlink/?LinkID=746217)</il><li>Run the following command:<br/>```Install-Module PowerShellGet -Force```</li></ol>|

> [!NOTE]
> Using PowerShellGet requires an Execution Policy that allows you to run scripts. For more
> information about PowerShell's Execution Policy, see
> [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
>
> [!IMPORTANT]
> The module described in this document, AzureRM, uses .NET Framework. This makes it incompatible with PowerShell 6.0,
> which uses .NET Core. If you are using PowerShell 6.0, follow the [installation instructions for
> macOS and Linux](/powershell/azure/install-az-ps).

## Install the Azure PowerShell module

You need elevated privileges to install modules from the PowerShell Gallery. To install Azure PowerShell,
run the following command in an elevated session:

```powershell-interactive
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

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `AzureRM` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
To learn how to persist your Azure sign in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Update the Azure PowerShell module

You can update your Azure PowerShell installation by running [Update-Module](/powershell/module/powershellget/update-module). This command does __not__ uninstall earlier versions.

```powershell-interactive
Update-Module -Name AzureRM
```

If you want to remove older versions of Azure PowerShell from your system, see [Uninstall the Azure PowerShell module](uninstall-azurerm-ps.md).

## Use multiple versions of Azure PowerShell

It's possible to install multiple versions of Azure PowerShell. You might need more than one version if you work with on-premises Azure Stack resources,
run an older version of Windows that you can't update to PowerShell 5.0, or use the Azure classic deployment model. To install an older version, provide the
`-RequiredVersion` argument when installing.

```powershell-interactive
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

When loading the Azure PowerShell module the latest version is loaded by default. To load a different version, provide the `-RequiredVersion` argument.

```powershell-interactive
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## Provide feedback

If you find a bug when using Azure Powershell, please [file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).
To provide feedback from the command line, use the [Send-Feedback](/powershell/module/azurerm.profile/send-feedback) cmdlet.

## Next Steps

To get started using Azure PowerShell, see [Get Started with Azure PowerShell](get-started-azureps.md) to learn more about the module and its features.
