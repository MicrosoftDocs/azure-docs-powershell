---
title: Other ways to install Azure PowerShell
description: How to install Azure PowerShell without PowerShellGet using an MSI
ms.devlang: powershell
ms.topic: conceptual

ms.custom: devx-track-azurepowershell
---

# Install Azure PowerShell on Windows with MSI

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

This article explains how to install Azure PowerShell on Windows using an MSI installer. Use these
installation methods only if they're necessary for your system. The recommended way to install Azure
PowerShell on Windows is with PowerShellGet. For instructions on using PowerShellGet to install
Azure PowerShell, see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

> [!NOTE]
> The Web Platform Installer method of installation is no longer available for versions of Azure
> PowerShell 6.x and higher. If you require use of the Web Platform Installer please consider using
> the MSI instead, or you can install an earlier version of Azure PowerShell.

## Install or update on Windows using the MSI Package

Azure PowerShell for Windows PowerShell 5.x can be installed using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/tag/v6.13.1-November2018). If you have
installed previous versions of Azure modules as an MSI, the installer automatically removes them.
The MSI package installs modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`. Both the
`AzureRM` and `Azure` modules are installed.

> [!NOTE]
> Only use the `Azure` module if you are working with the Azure classic deployment model.

To start working with Azure PowerShell, sign in with your Azure credentials.

```azurepowershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> If you've disabled module autoloading, you need to manually import the module with
> `Import-Module -Name AzureRM`. Because of the way the module is structured, this can take a few
> seconds.

You'll need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Persist user credentials across PowerShell sessions](context-persistence.md).
