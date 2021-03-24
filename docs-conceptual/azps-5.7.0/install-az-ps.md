---
title: Install the Azure Az PowerShell module with PowerShellGet
description: How to install the Azure Az PowerShell with PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/22/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Install the Azure Az PowerShell module

This article explains how to install the Azure Az PowerShell module using
[PowerShellGet](/powershell/scripting/gallery/installing-psget). These instructions work on Windows,
macOS, and Linux platforms.

The Azure Az PowerShell module is preinstalled in Azure
[Cloud Shell](/azure/cloud-shell/overview) and in [Docker images](azureps-in-docker.md).

The Azure Az PowerShell module is a rollup module. Installing it downloads the generally available
Az PowerShell modules, and makes their cmdlets available for use.

## Requirements

> [!NOTE]
> PowerShell 7.x and later is the recommended version of PowerShell for use with the Azure Az
> PowerShell module on all platforms.

 The Azure Az PowerShell module works with PowerShell 7.x and later on all platforms. Azure
 PowerShell has no additional requirements when run on PowerShell 7.x and later.

- Install the
 [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for
 your operating system.

To check your PowerShell version, run the following command from within a PowerShell session:

```azurepowershell-interactive
$PSVersionTable.PSVersion
```

## Installation

Using the [Install-Module](/powershell/module/powershellget/install-module) cmdlet is the preferred
installation method for the Az PowerShell module. Install the Az module for the current user only.
This is the recommended installation scope. This method works the same on Windows, macOS, and Linux
platforms. Run the following command from a PowerShell session:

```powershell-interactive
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```

## Other Installation Options

While PowerShell 7.x is the recommended version of PowerShell, and `Install-Module` is the
recommended installation option, there are additional installation options if needed.

### Installation on Windows PowerShell

The Azure Az PowerShell module is also supported for use with PowerShell 5.1 on Windows. To use the
Azure Az PowerShell module in PowerShell 5.1 on Windows:

1. Update to
   [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.
2. Install [.NET Framework 4.7.2 or later](/dotnet/framework/install).
3. Make sure you have the latest version of PowerShellGet. Run `Install-Module -Name PowerShellGet -Force`.

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

```powershell-interactive
Connect-AzAccount
```

## Update the Azure PowerShell module

To update any PowerShell module, you should use the same method used to install the module. For
example, if you originally used `Install-Module`, then you should use
[Update-Module](/powershell/module/powershellget/update-module) to get the latest version. If you
originally used the MSI package, then you should download and install the new MSI package.

The PowerShellGet cmdlets cannot update modules that were installed from an MSI package. MSI
packages do not update modules that were installed using PowerShellGet. If you have any issues
updating using PowershellGet, then you should **reinstall**, rather than **update**. Reinstalling is
done the same way as installing. Ensure you use the `Force` parameter with `Install-Module` when
reinstalling.

Unlike MSI-based installations, installing or updating using PowerShellGet does not remove older
versions that may exist on your system. To remove old versions of the Az PowerShell module from your
system, see [Uninstall the Azure PowerShell module](uninstall-az-ps.md). For more information about
MSI-based installations, see [Install Azure PowerShell with an MSI](install-az-ps-msi.md).

## Troubleshooting

Here are some common problems seen when installing the Azure Az PowerShell module. If you experience
a problem not listed here,
[file an issue on GitHub](https://github.com/azure/azure-powershell/issues).

### Az and AzureRM coexistence

> [!WARNING]
> We do not support having both the AzureRM and Az modules installed for PowerShell 5.1 on Windows
> at the same time.

In a scenario where you want to install both AzureRM and the Az PowerShell module on the same
system, AzureRM must be installed only in the user scope for Windows PowerShell. Install the Az
PowerShell module for PowerShell 7.x on the same system.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

### Proxy blocks connection

If you get errors from `Install-Module` that the PowerShell Gallery is unreachable, you may be
behind a proxy. Different operating systems and network environment have different requirements for
configuring a system-wide proxy. Contact your system administrator for your proxy settings and how
to configure them for your environment.

PowerShell itself may not be configured to use this proxy automatically. With PowerShell 5.1 and
later, configure the PowerShell session to use a proxy using the following commands:

```powershell
$webClient = New-Object -TypeName System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

If your operating system credentials are configured correctly, this configuration routes PowerShell
requests through the proxy. To have this setting persist between sessions, add the commands to your
[PowerShell profile](/powershell/module/microsoft.powershell.core/about/about_profiles).

To install the package, your proxy needs to allow HTTPS connections to `https://www.powershellgallery.com`.

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
