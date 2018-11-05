---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating scripts from the AzureRM module to the new Az module.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/01/2018
---

# Migrate from AzureRM to Azure PowerShell Az

With the introduction of the Az module, older scripts which use the AzureRM modules and cmdlets no
longer work automatically. No migration that changes command names is ever convenient or easy to
handle. In order to help with the process of changing all your scripts over from AzureRM to Az,
this article will outline steps, tools, and scripts that you can take advantage of to automate
the process of migrating to Az as easy as possible.

Each section of this article outlines a step in the process, and it's recommended that you follow
them in order unless you've already completed the process outlined in a single step.

## Ensure your existing scripts work with the latest AzureRM release

This is the most important step! Run your existing scripts, and make sure that they work with the
_latest_ release of AzureRM (__6.11.0__). If your scripts do not work, make sure to go through and read
the [AzureRM migration guide](/powershell/azure/migration-guide.6.0.0).

## Install the Azure PowerShell Az module

The first step is to install the Az module on your platform. This _does_ require uninstalling
the AzureRM module, but the following steps will outline how you can get compatibility with the old
command set until your migration is completed.

To install the Azure PowerShell Az module, follow these steps:

* [Uninstall the AzureRM module](/powershell/azure/uninstall-azurerm-ps?view=azurermps-6.11.0). Make sure that
you remove _all_ installed versions of AzureRM, not just the most recent version.
* [Install the Az module](install-az-ps.md)

## <a name="aliases"/>Enable AzureRM alias mode

With AzureRM uninstalled and your scripts working with the latest AzureRM version, now is the time to
enable the compatibility mode for the Az module. This is done with the command

```powershell
Enable-AzureRmAlias -Scope CurrentUser
```

This enables the ability to use old cmdlet names with the `Az` module installed, through aliases. These
aliases are written to the user profile for the selected scope. If no user profile exists, one is created.

> [!WARNING]
>
> You can use a different `-Scope` for this command, but it's not recommended! Because the aliases are written to
> the user profile for the selected scope, keep enabling them to as limited a scope as possible. Enabling aliases
> system-wide could also cause issues for other users which have AzureRM installed in their local scope.

Once the alias mode is enabled, run your scripts again to confirm that they still function as expected. 

## Change module imports and cmdlet names

In general, the module names have been changed so that `AzureRM` becomes `Az`, and the same for cmdlets.
For example, the `AzureRM.Compute` module has been renamed to `Az.Compute`. `New-AzureRmVM` has become `New-AzVM`.
There are some exceptions to this naming change that you should be aware of before doing any renaming:

| AzureRM module | Az module |
|----------------|-----------|
| Azure.Storage | Az.Storage |
| Azure.AnalysisServices | Az.AnalysisServices |
| AzureRM.DataFactories | Az.DataFactory |
| AzureRM.DataFactoryV2 | Az.DataFactory |
| AzureRM.RecoveryServices.Backup | Az.RecoveryServices |
| AzureRM.RecoveryServices.SiteRecovery | Az.RecoveryServices |

In the case of `Azure.Storage` and `Azure.AnalysisServices`, the associated cmdlets have also been renamed
so that `Azure` is replaced with `Az`. For example, `Get-AzureStorageBlob` has been renamed to `Get-AzStorageBlob`.

To help with the renaming of modules and cmdlets in your scripts, you can use the following PowerShell script
to automate most of the work. You will still need to make sure that the script runs at the end of the edits,
but the number of changes you have to make on your own will hopefully be much fewer!

```powershell
function Update-AzureRmScript {
    param(
        [Parameter(mandatory=$true)]
        [string]$File
    )

    $replacements = @(
        @{
            "name"="Azure.Storage"
            "module"="Az.Storage"
        },
        @{
            "name"="Azure.AnalysisServices"
            "module"="Az.AnalysisServices"
        },
        @{
            "name"="AzureRM.DataFactories"
            "module"="Az.DataFactory"
            "moduleOnly"=$true
        },
        @{
            "name"="AzureRM.DataFactoryV2"
            "module"="Az.DataFactory"
            "moduleOnly"=$true
        },
        @{
            "name"="AzureRM.RecoveryServices.Backup"
            "module"="Az.RecoveryServices"
            "moduleOnly"=$true
        },
        @{
            "name"="AzureRM.RecoveryServices.SiteRecovery"
            "module"="Az.RecoveryServices"
            "moduleOnly"=$true
        }
    )

    echo "Updating $File..."
    $content = Get-Content $file
    for ($i=0; $i -lt $content.Length; $i++) {
        $line = $content[$i]
        if ($line -match "^\s*Import-Module.+(AzureRm)") {
            $content[$i] = $line -replace $matches[1],"Az"
        }
        elseif ($line -match "[A-Za-z]+-(AzureRm)") {
            $content[$i] = $line -replace $matches[1],"Az"
        }
        else {
            foreach ($module in $renames) {
                if ($line -match "^\s*Import-Module.+($($module.Name))") {
                    $content[$i] = $line -replace $matches[1],$module.Module
                }
                elseif ((-not $module.moduleOnly) -and ($line -match "[A-Za-z]+-($($module.Module))")) {
                    $content[$i] = $line -replace $matches[1],$module.Module
                }
            }
        }
    }
    Set-Content -Path $file -Value $content -Force
}
```

> [!IMPORTANT]
>
> If you used `AzureRM` as part of any of your function names in your script, those commands will be renamed to
> use `Az` instead. As long as you also update all scripts which call these functions, that shouldn't
> cause a problem. Just be aware that this script __will__ change all function and command names
> containing `AzureRM`.

## Disable AzureRM aliases

When you've completed your script migration and no longer need AzureRM compatibility, you should disable the cmdlet
aliases. This is done with the `Disable-AzureRmAlias` command:

```powershell
Disable-AzureRmAlias -Scope CurrentUser
```

If you provided a different value for `-Scope` when enabling aliases, make sure that you use it here as well.

## Summary

By following these steps, you can update all of your existing scripts to use the new module without a lot of pain or difficulty. If you have any questions or encountered problems with these steps that made your migration difficult, please feel free to comment on this article so that we can improve the instructions.