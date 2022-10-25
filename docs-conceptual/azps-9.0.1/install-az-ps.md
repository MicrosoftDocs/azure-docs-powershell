---
description: How to install the Azure Az PowerShell module from the PowerShell Gallery
ms.custom: devx-track-azurepowershell
ms.date: 10/18/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Install the Azure Az PowerShell module
---

# Install the Azure Az PowerShell module

This article explains how to install the Azure Az PowerShell module from
[The PowerShell Gallery](/powershell/scripting/gallery/overview). These instructions work on
Windows, Linux, and macOS platforms.

The Azure Az PowerShell module is preinstalled in Azure
[Cloud Shell](/azure/cloud-shell/overview) and in [Docker images](azureps-in-docker.md).

The Azure Az PowerShell module is a rollup module. Installing it downloads the generally available
Az PowerShell modules, and makes their cmdlets available for use.

## Requirements

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, or higher is the recommended version of PowerShell for
> use with the Azure Az PowerShell module on all platforms.

Azure PowerShell has no additional requirements when run on PowerShell 7.0.6 LTS and PowerShell
7.1.3 or higher.

- Install the
 [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for
 your operating system.

To check your PowerShell version, run the following command from within a PowerShell session:

```powershell
$PSVersionTable.PSVersion
```

PowerShell script execution policy must be set to remote signed or less restrictive.
`Get-ExecutionPolicy -List` can be used to determine the current execution policy. For more
information, see
[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## Installation

Using the [Install-Module](/powershell/module/powershellget/install-module) cmdlet is the preferred
installation method for the Az PowerShell module. Install the Az module for the current user only.
This is the recommended installation scope. This method works the same on Windows, Linux, and macOS
platforms. Run the following command from a PowerShell session:

```powershell
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```

## Other Installation Options

While PowerShell 7.0.6 LTS, PowerShell 7.1.3, or higher is the recommended version of PowerShell,
and `Install-Module` is the recommended installation option, there are additional installation
options if needed.

### Installation on Windows PowerShell

> [!IMPORTANT]
> If you have the AzureRM PowerShell module installed, see
> [Az and AzureRM coexistence](troubleshooting.md#az-and-azurerm-coexistence)
> before proceeding.

The Azure Az PowerShell module is also supported for use with PowerShell 5.1 on Windows. To use the
Azure Az PowerShell module in PowerShell 5.1 on Windows:

1. Update to
   [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.
1. Install [.NET Framework 4.7.2 or later](/dotnet/framework/install).
1. Make sure you have the latest version of PowerShellGet. Run `Install-Module -Name PowerShellGet -Force`.

### Offline Installation

In some environments, it's not possible to connect to the PowerShell Gallery. In those situations,
you can install the Az PowerShell module offline using one of these methods:

- [Download the Azure PowerShell MSI](install-az-ps-msi.md). Keep in mind that the MSI installer
  only works for PowerShell 5.1 on Windows.
- Download the modules to another location in your network and use that as an installation source.
  This method allows you to cache PowerShell modules on a single server or file share to be deployed
  with PowerShellGet to any disconnected systems. Learn how to set up a local repository and install
  on disconnected systems with
  [Working with local PowerShellGet repositories](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
- Save the module with [Save-Module](/powershell/module/PowershellGet/Save-Module) to a file share,
  or save it to another source and manually copy it to other machines.

## Sign in

To start working with Azure PowerShell, sign in with your Azure credentials.

```azurepowershell
Connect-AzAccount
```

After executing this command, a new browser window pops up and you can log into your Azure account.

## Update the Azure PowerShell module

To update any PowerShell module, you should use the same method used to install the module. For
example, if you originally used `Install-Module`, then you should use
[Update-Module](/powershell/module/powershellget/update-module) to get the latest version. If you
originally used the MSI package, then you should download and install the new MSI package.

The PowerShellGet cmdlets cannot update modules that were installed from an MSI package. MSI
packages do not update modules that were installed using PowerShellGet. If you have any issues
updating using PowerShellGet, then you should **reinstall**, rather than **update**. Reinstalling is
done the same way as installing. Ensure you use the `Force` parameter with `Install-Module` when
reinstalling.

Unlike MSI-based installations, installing or updating using PowerShellGet does not remove older
versions that may exist on your system.

> [!NOTE]
> Uninstallation can be complicated if you have more than one version of the Az PowerShell module
> installed. Because of this complexity, we only support uninstalling all versions of the Az
> PowerShell module that are currently installed.

To remove all versions of the Az PowerShell module from your system, see
[Uninstall the Azure PowerShell module](uninstall-az-ps.md). For more information about MSI-based
installations, see [Install Azure PowerShell with an MSI](install-az-ps-msi.md).

## Troubleshooting

[Troubleshoot installation problems with the Azure Az PowerShell module](troubleshooting.md#installation).

## Provide feedback

If you find a bug in the Azure Az PowerShell module,
[file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). To provide feedback
from within a PowerShell session, use the
[Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.

## Next Steps

To learn more about the Azure Az PowerShell modules and their features, see
[Get Started with Azure PowerShell](get-started-azureps.md). If you're familiar with Azure
PowerShell and need to migrate from AzureRM, see
[Migrate from AzureRM to Az](migrate-from-azurerm-to-az.md).
