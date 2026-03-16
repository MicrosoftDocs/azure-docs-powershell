---
description: Learn the steps and tools for migrating Azure PowerShell scripts from AzureRM to the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Migrate Azure PowerShell scripts from AzureRM to Az
---

# Migrate Azure PowerShell from AzureRM to Az

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## Determine if you're using the AzureRM PowerShell module

Use the following command to determine if you have the AzureRM PowerShell module installed:

```powershell
Get-Module -Name AzureRM -ListAvailable
```

You can also perform a full text search of your scripts for the pattern `*-AzureRM*` to determine if
any of them are using the AzureRM PowerShell module.

## Upgrade to the Az PowerShell module

Scripts written for the AzureRM cmdlets won't automatically work with Az. To make the transition
easier, the [AzureRM to Az migration toolkit](/powershell/azure/migration-overview) was developed.
No migration to a new command set is ever convenient, but this article will help you get started on
transitioning to the Az PowerShell module. To learn more about why the Az PowerShell module was
created, see [Introducing the Az PowerShell module](new-azureps-module-az.md).

The new cmdlet names have been designed to be easy to learn. Instead of using `AzureRm` or `Azure`
in cmdlet names, use `Az`. For example, the old cmdlet `New-AzureRMVm` has become `New-AzVm`.
However, migration is more than becoming familiar with the new cmdlet names, though. There are
renamed modules, parameters, and other important changes.

To see the full list of breaking changes between AzureRM and Az, see the
[full changes from AzureRM to Az](migrate-az-1.0.0.md).

## Ensure existing scripts work with the latest AzureRM release

Before taking any migration steps, determine what versions of AzureRM are installed on your system.
Doing so allows you to make sure scripts are already running on the latest release and let you know
what versions of AzureRM must be uninstalled.

To determine what versions of AzureRM you have installed, run the following example:

```powershell
Get-Module -Name AzureRM -ListAvailable -All
```

The **latest** available release of AzureRM is **6.13.2**. If you don't have this version installed,
your existing scripts may need additional modifications to work with the Az module beyond the scope
of what's described in this article and in the [breaking changes list](migrate-az-1.0.0.md).

If your scripts don't work with AzureRM 6.13.2, update them according to the
[AzureRM 5.x to 6.x migration guide](/previous-versions/powershell/azure/migration-guide.6.0.0). If
you use an earlier version of the AzureRM module, there are migration guides available for each
major version.

## Option 1 (recommended): Automatically migrate your PowerShell scripts

This recommended option minimizes the effort required to migrate AzureRM scripts to Az.

With the AzureRM to Az migration toolkit, you can generate a plan to determine what changes will be
performed on your scripts before making any modifications to them and before installing the Az
PowerShell module.

The [Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module](quickstart-migrate-azurerm-to-az-automatically.md)
quickstart walks you through the entire process of automatically updating your PowerShell scripts
from AzureRM to the Az PowerShell module.

## Option 2: Use compatibility mode with Enable-AzureRmAlias

The Az module has a compatibility mode to help you use existing scripts while you update to the new
syntax. The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet enables
a compatibility mode through aliases. This mode allows you to use existing scripts with minimal
modification while working towards a full migration to Az. By default, `Enable-AzureRmAlias` only
enables compatibility aliases for the current PowerShell session. Use its `Scope` parameter to
persist compatibility aliases across PowerShell sessions. For more information, see
[the Enable-AzureRmAlias reference documentation](/powershell/module/az.accounts/enable-azurermalias).

> [!IMPORTANT]
> Even though the cmdlet names are aliased, there may still be new (or renamed) parameters or
> changed return values for the Az cmdlets. Don't expect enabling aliases to take care of the
> migration for you. See the [full breaking changes list](migrate-az-1.0.0.md) to find where your
> scripts may require updates.

Support for `Enable-AzureRmAlias` will not be deprecated with the deprecation of the AzureRM
PowerShell module.

## Next steps

- [Automatically migrate PowerShell scripts](quickstart-migrate-azurerm-to-az-automatically.md)
- [Introducing the Az PowerShell module](new-azureps-module-az.md)
- [Changes between AzureRM and Az](migrate-az-1.0.0.md)
- [Install the Az PowerShell module](install-azure-powershell.md)
- [Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
