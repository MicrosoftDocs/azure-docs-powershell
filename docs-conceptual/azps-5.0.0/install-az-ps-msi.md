---
title: Install Azure PowerShell with an MSI
description: How to install Azure PowerShell without PowerShellGet using an MSI
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/10/2020 
ms.custom: devx-track-azurepowershell 
ms.service: azure-powershell
---

# Install Azure PowerShell on Windows with MSI

This article explains how to install Azure PowerShell on Windows using an MSI installer. The MSI
installer is provided for environments where the PowerShell Gallery may be blocked by a firewall, or
an offline installer is needed. The recommended way to install Azure PowerShell is with
PowerShellGet. For instructions on using PowerShellGet to install Azure PowerShell, see
[Install Azure PowerShell with PowerShellGet](install-az-ps.md).

## Requirements

The MSI installer on Windows is designed to install Azure PowerShell for PowerShell 5.1 only. For
installation on non-Windows platforms or later versions of PowerShell,
[Install with PowerShellGet](install-az-ps.md). To check your PowerShell version, run the command:

```powershell-interactive
$PSVersionTable.PSVersion
```

To use Azure PowerShell in PowerShell 5.1, you need to:

1. Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)
   if needed. If you're on Windows 10, you already have PowerShell 5.1 installed.
2. Install [.NET Framework 4.7.2 or later](/dotnet/framework/install).

## Install or update on Windows using the MSI Package

The MSI package for Azure PowerShell is available from
[GitHub](https://github.com/Azure/azure-powershell/releases):

1. Go to https://github.com/Azure/azure-powershell/releases.
2. Look for the most recent Gallery Module for Azure PowerShell (these are listed chronologically and are typically just a release version with no name like "4.7.0").
3. Scroll down to the bottom of the patch notes and click on the arrow next to "Assets" to reveal the MSI options.
4. Click on the Az-Cmdlets MSI of your choice to start the download.

If you have installed earlier
versions of Azure PowerShell using the MSI, the installer automatically removes them. The MSI
package installs modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`.

To start working with Azure PowerShell, sign in with your Azure credentials.

```powershell-interactive
# Connect to Azure with an interactive dialog for sign-in
Connect-AzAccount
```

> [!NOTE]
> If you've disabled module autoloading, you need to manually import the module with
> `Import-Module Az`. Because of the way the module is structured, this can take up to a minute.

You'll need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Persist user credentials across PowerShell sessions](context-persistence.md).

## Provide feedback

If you find a bug in Azure PowerShell,
[file an issue on GitHub](https://github.com/Azure/azure-powershell/issues). To provide feedback
from the command line, use the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.

## Next Steps

To learn more about the Azure PowerShell modules and their features, see
[Get Started with Azure PowerShell](get-started-azureps.md). If you're familiar with Azure
PowerShell and need to migrate from AzureRM, see
[Migrate from AzureRM to Az](migrate-from-azurerm-to-az.md).
