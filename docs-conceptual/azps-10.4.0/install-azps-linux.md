---
description: Learn how to install and run Azure PowerShell on Linux. You can install Azure PowerShell on Linux with one command.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Install Azure PowerShell on Linux
---


# Install Azure PowerShell on Linux

The Azure PowerShell Az module is a rollup module. Installing it downloads the generally available
Az PowerShell modules and makes their cmdlets available for use.

This article explains how to install the Az PowerShell module on Linux.

## Prerequisites

- Install a supported version of [PowerShell version 7 or higher](/powershell/scripting/install/installing-powershell-on-linux)

## Installation

Open the Terminal or other shell host application and run `pwsh` to start PowerShell.

Use the [Install-Module](/powershell/module/powershellget/install-module) cmdlet to install the Az
PowerShell module:

```powershell
Install-Module -Name Az -Repository PSGallery -Force
```

## Update the Az PowerShell module

Use [Update-Module](/powershell/module/powershellget/update-module) to update to the latest version
of the Az PowerShell module:

```powershell
Update-Module -Name Az -Force
```

Updating the Az PowerShell module using `Update-Module` doesn't remove old versions of the Az
PowerShell module from your system.

## Uninstallation

To remove the Az PowerShell module from your system, see
[Uninstall the Azure PowerShell module](uninstall-az-ps.md).

## Sign in

To start managing your Azure resources with the Az PowerShell module, launch a PowerShell session
and run `Connect-AzAccount` to sign in to Azure:

```azurepowershell
Connect-AzAccount
```

Use your Azure account login credentials to log into the browser window that opens.

You'll need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Azure PowerShell context objects](/powershell/azure/context-persistence).

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Azure Az PowerShell module](troubleshooting.md#installation).

## Provide feedback

To file an issue about the Az PowerShell module, see:
[file an issue on GitHub](https://github.com/Azure/azure-powershell/issues).

To provide feedback from within a PowerShell session, use the
[Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.

## Next Steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell](get-started-azureps.md).
