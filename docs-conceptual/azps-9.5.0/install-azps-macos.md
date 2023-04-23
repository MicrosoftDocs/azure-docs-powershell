---
description: Learn how to install and run Azure PowerShell on macOS. You can install Azure PowerShell on macOS with one command.
ms.custom: devx-track-azurepowershell
ms.date: 03/31/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Install Azure PowerShell on macOS | Microsoft Docs
---

# Install Azure PowerShell on macOS

This article explains how to install the Azure PowerShell Az module from
[the PowerShell Gallery][01] on macOS.

The Az PowerShell module is a rollup module. Installing it downloads the generally available Az
PowerShell modules and makes their cmdlets available for use.

## Prerequisites

- Install a supported version of [PowerShell version 7 or higher][02]

## Installation

Open the Terminal or other shell host application and run `pwsh` to start PowerShell.

Use the [Install-Module][03] cmdlet to install the Az PowerShell module:

```powershell
Install-Module -Name Az -Repository PSGallery -Force
```

## Update the Azure PowerShell module

Use the [Update-Module][04] cmdlet to update to the
latest version of the Az PowerShell module.

```powershell
Update-Module -Name Az -Force
```

Updating the Az PowerShell module using `Update-Module` doesn't remove old versions of the Az
PowerShell module from your system.

## Uninstallation

To remove the Az PowerShell module from your system, see
[Uninstall the Azure PowerShell module][05].

## Sign in

To start managing your Azure resources with the Az PowerShell module, launch a PowerShell session
and run `Connect-AzAccount` to sign in to Azure:

```azurepowershell
Connect-AzAccount
```

Use your Azure account login credentials to log into the browser window that opens.

You'll need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see [Azure PowerShell context objects][06].

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Az PowerShell module][07].

## Provide feedback

To file an issue about the Az PowerShell module, see: [file an issue on GitHub][08].

To provide feedback from within a PowerShell session, use the [Send-Feedback][09] cmdlet.

## Next steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell][10].

<!-- link references -->
[01]: /powershell/gallery/overview
[02]: /powershell/scripting/install/installing-powershell-on-macos
[03]: /powershell/module/powershellget/install-module
[04]: /powershell/module/powershellget/update-module
[05]: uninstall-az-ps.md
[06]: /powershell/azure/context-persistence
[07]: troubleshooting.md#installation
[08]: https://github.com/Azure/azure-powershell/issues
[09]: /powershell/module/az.accounts/send-feedback
[10]: get-started-azureps.md
