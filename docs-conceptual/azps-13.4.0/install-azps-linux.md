---
description: Learn how to install and run Azure PowerShell on Linux to manage your Azure resources with PowerShell. Step-by-step guide for seamless installation and updates.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Install Azure PowerShell on Linux
---

# Install Azure PowerShell on Linux

This article explains how to install the Az PowerShell module from
[the PowerShell Gallery][powershell-gallery] on Linux.

The Az PowerShell module is a rollup module. Installing it downloads the generally available Az
PowerShell modules and makes their cmdlets available for use.

## Prerequisites

- Install a supported version of [PowerShell version 7 or higher][install-pwsh-linux]

## Installation

Open the Terminal or other shell host application and run `pwsh` to start PowerShell.

Use the [Install-Module][install-module] cmdlet to install the Az PowerShell module:

```powershell
Install-Module -Name Az -Repository PSGallery -Force
```

## Update the Az PowerShell module

Use the [Update-Module][update-module] cmdlet to update to the latest version of the Az PowerShell
module:

```powershell
Update-Module -Name Az -Force
```

Updating the Az PowerShell module using `Update-Module` doesn't remove old versions of the Az
PowerShell module from your system.

## Uninstallation

To remove the Az PowerShell module from your system, see
[Uninstall the Azure PowerShell module][uninstall-azps].

## Sign in

To start managing your Azure resources with the Az PowerShell module, launch a PowerShell session
and run `Connect-AzAccount` to sign in to Azure:

```azurepowershell
Connect-AzAccount
```

Use your Azure account login credentials to log into the browser window that opens.

You need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Azure PowerShell context objects][azps-context-objects].

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Az PowerShell module][troubleshoot-azps-install].

## Provide feedback

To file an issue about the Az PowerShell module, see [file an issue on GitHub][azps-github-issue].
To provide feedback from within a PowerShell session, use the [Send-Feedback][send-feedback] cmdlet.

## Next Steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell][get-started-azps].

<!-- link references -->

[powershell-gallery]: /powershell/scripting/gallery/overview
[install-pwsh-linux]: /powershell/scripting/install/installing-powershell-on-linux
[install-module]: /powershell/module/powershellget/install-module
[update-module]: /powershell/module/powershellget/update-module
[uninstall-azps]: uninstall-az-ps.md
[azps-context-objects]: /powershell/azure/context-persistence
[troubleshoot-azps-install]: troubleshooting.md#installation
[azps-github-issue]: https://github.com/Azure/azure-powershell/issues
[send-feedback]: /powershell/module/az.accounts/send-feedback
[get-started-azps]: get-started-azureps.md
