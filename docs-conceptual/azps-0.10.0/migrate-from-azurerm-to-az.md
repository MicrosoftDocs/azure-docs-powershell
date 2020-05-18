---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating scripts from the AzureRM module to the new Az module.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/10/2019
---

# Migrate Azure PowerShell from AzureRM to Az

The Az module has feature parity with AzureRM, but uses shorter and more consistent cmdlet names.
Scripts written for the AzureRM cmdlets won't automatically work with the new
module. To make the transition easier, Az offers tools to allow you to run your existing scripts
using AzureRM. No migration to a new command set is ever convenient, but this article will help
you get started on transitioning to the new module.

To see the full list of breaking changes between AzureRM and Az, see the
[full changes from AzureRM to Az](migrate-az-1.0.0.md).

## Ensure existing scripts work with the latest AzureRM release

Before taking any migration steps, check which versions of AzureRM are installed on your system. Doing so
allows you to make sure scripts are already running on the latest release, and let you know which
versions of AzureRM must be uninstalled.

To check which version(s) of AzureRM you have installed, run the command:

```powershell-interactive
Get-InstalledModule -Name AzureRM -AllVersions
```

The __latest__ available release of AzureRM is __6.13.1__. If you don't have this version installed,
your existing scripts may need additional modification to work with the Az module beyond what's
described here and in the [breaking changes list](migrate-az-1.0.0.md).

If your scripts don't work with AzureRM 6.13.1, update them according to the
[AzureRM 5.x to 6.x migration guide](/powershell/azure/azurerm/migration-guide.6.0.0).
If you use an earlier version of the AzureRM module, there are migration guides available for
each major version.

## Uninstall AzureRM

The Az module is not guaranteed to be compatible with any existing AzureRM installs in
PowerShell 5.1 for Windows. Before you install the Az module,
[uninstall AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module).

> [!IMPORTANT]
>
> If you're not ready to remove the AzureRM module from your system, you can install the Az
> module for [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows)
> 6.x or later instead. PowerShell Core and PowerShell 5.1 for Windows use different module libraries,
> so there will be no conflicts. You can still [enable aliases](#enable-azurerm-compatibility-aliases) in PowerShell Core.

## Install the Azure PowerShell Az module

The first step is to install the Az module on your platform. When you install Az, it's recommended
that you uninstall AzureRM. In the following steps, you'll learn how to keep running your existing
scripts and enable compatibility for old cmdlet names.

To install the Azure PowerShell Az module, follow the instructions in [Install the Az module](install-az-ps.md).

> [!NOTE]
> At this point, you might want to run the [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm)
> cmdlet provided in the Az module, just to make sure that all versions of AzureRM have been uninstalled
> and won't cause conflicts.

## Enable AzureRM compatibility aliases

With AzureRM uninstalled and your scripts working with the latest AzureRM version, the next step is to 
enable the compatibility mode for the Az module. Compatibility is enabled with the command:

```powershell-interactive
Enable-AzureRmAlias -Scope CurrentUser
```

Aliases enable the ability to use old cmdlet names with the Az module installed. These
aliases are written to the profile for the selected scope. If no profile exists, one is created.
When using a `-Scope` broader than `CurrentUser`, the appropriate permissions are required to create or
update the corresponding profile file.

> [!IMPORTANT]
> __Only__ cmdlet names are aliased - module names aren't! If you're using `#Requires`, `Import-Module`,
> dependency lists in a `.psd1`, or fully-qualified cmdlet names, make sure that you migrate them at this point
> by following the process outlined in the [breaking changes list](migrate-az-1.0.0.md) regarding module names.

> [!WARNING]
>
> You can use a different `-Scope` for this command, but it's not recommended. Aliases are written to
> the user profile for the selected scope, so keep enabling them to as limited a scope as possible. Enabling aliases
> system-wide can cause issues for other users who have AzureRM installed in their local scope.

Once the alias mode is enabled, run your scripts again to confirm that they still function as expected.
Some parameter names have been changed, added, or made required by the Az module. Output types of cmdlets
may have changed as well. These changes are detailed in the [breaking changes list](migrate-az-1.0.0.md).

## Update cmdlets, modules, and parameters

With scripts updated and running under aliases, you can take your time to update them to use the new
cmdlets and take advantage of other changes like new features. For most scripts, you will only need
to update cmdlet names, [following the new cmdlet naming scheme in Az](migrate-az-1.0.0.md#cmdlet-noun-prefix-changes). There may also be some other changes
that you need to make in order to have your scripts work, depending on what they do and which Azure
PowerShell features they take advantage of.

For example, the [Blob Storage cmdlets](migrate-az-1.0.0.md#azstorage-previously-azurestorage-and-azurermstorage) have been completely reworked to use a new asynchronous model,
so scripts using them will take more work to update than those where the only relevant changes were cmdlet
names.

Even if you've only had to make small, simple changes to your scripts up to this point - or they
even work without additional modification when aliases are enabled -  read the [full list
of breaking changes in Az 1.0.0](migrate-az-1.0.0.md) to make sure that you're not relying on
'transparent' behavior of aliases which could disappear after you change cmdlet names and disable
aliases.

## Disable aliases

Once you've completed your migration and are no longer relying on aliasing behavior, it's recommended
that you disable aliases. This is done with the [Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias) cmdlet.

> [!IMPORTANT]
> When running this cmdlet, __make sure__ that you invoke it for each `-Scope` that `Enable-AzureRmAlias`
> was invoked for, otherwise there may still be scripts on your system relying on the aliasing behavior.
