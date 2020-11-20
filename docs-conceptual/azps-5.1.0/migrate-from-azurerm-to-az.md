---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating scripts from the AzureRM module to the new Az module.
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.date: 10/12/2020
ms.custom: devx-track-azurepowershell
---

# Migrate Azure PowerShell from AzureRM to Az

All versions of the AzureRM PowerShell module are outdated, but not out of support. The [Az
PowerShell module](install-az-ps.md) is now the recommended PowerShell module for interacting with
Azure.

Scripts written for the AzureRM cmdlets won't automatically work with the new module. To make the
transition easier, the
[AzureRM to Az migration toolkit](https://github.com/Azure/azure-powershell-migration) was
developed. No migration to a new command set is ever convenient, but this article will help you get
started on transitioning to the Az PowerShell module. To learn more about why the Az PowerShell
module was created, see [Introducing the new Azure PowerShell Az module](new-azureps-module-az.md).

To see the full list of breaking changes between AzureRM and Az, see the
[full changes from AzureRM to Az](migrate-az-1.0.0.md).

## Ensure existing scripts work with the latest AzureRM release

Before taking any migration steps, check which versions of AzureRM are installed on your system.
Doing so allows you to make sure scripts are already running on the latest release, and let you know
which versions of AzureRM must be uninstalled.

To check which version(s) of AzureRM you have installed, run the following example:

```azurepowershell
Get-Module -Name AzureRM -ListAvailable -All
```

The **latest** available release of AzureRM is **6.13.1**. If you don't have this version installed,
your existing scripts may need additional modifications to work with the Az module beyond what's
described in this article and in the [breaking changes list](migrate-az-1.0.0.md).

If your scripts don't work with AzureRM 6.13.1, update them according to the
[AzureRM 5.x to 6.x migration guide](/powershell/azure/azurerm/migration-guide.6.0.0). If you use an
earlier version of the AzureRM module, there are migration guides available for each major version.

## Install the AzureRM to Az migration toolkit

```azurepowershell
Install-Module -Name Az.Tools.Migration
```

## Automatically migrate your PowerShell scripts

With the AzureRM to Az migration toolkit, you can generate a plan to determine what changes will be
performed on your scripts before making any modifications to them and before installing the Az
PowerShell module.

The [Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module](quickstart-migrate-azurerm-to-az-automatically.md) quickstart walks you through the entire process of automatically updating your PowerShell scripts from AzureRM to the Az PowerShell module.

## Next steps

[Install Azure PowerShell](install-az-ps.md)
[Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
