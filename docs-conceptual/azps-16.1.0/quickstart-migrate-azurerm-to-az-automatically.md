---
description: Learn how to automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module.
ms.custom: devx-track-azurepowershell, mode-api
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: quickstart
title: Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module
---

# Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module

In this article, you'll learn how to use the [Az.Tools.Migration](/powershell/module/az.tools.migration/) PowerShell module to automatically
upgrade your PowerShell scripts and script modules from AzureRM to the Az PowerShell module. For
additional migration options, see
[Migrate Azure PowerShell from AzureRM to Az](/powershell/azure/migrate-from-azurerm-to-az).

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## Requirements

- Update your existing PowerShell scripts to the latest version of the
  [AzureRM PowerShell module (6.13.1)](https://www.powershellgallery.com/packages/AzureRM/).
- Install the Az.Tools.Migration PowerShell module.

  ```powershell
  Install-Module -Name Az.Tools.Migration
  ```

## Generate an AzureRM-to-Az upgrade plan

You use the [**`New-AzUpgradeModulePlan`**](/powershell/module/az.tools.migration/new-azupgrademoduleplan) cmdlet to generate an upgrade plan for migrating your
scripts and modules to the Az PowerShell module. This cmdlet doesn't make any changes to your
existing scripts. Use the **`FilePath`** parameter for targeting a specific script or the
**`DirectoryPath`** parameter for targeting all scripts in a specific folder.

The following table lists the key parameters for `New-AzUpgradeModulePlan` and `Invoke-AzUpgradeModulePlan`:

| Cmdlet | Parameter | Description |
|--------|-----------|-------------|
| `New-AzUpgradeModulePlan` | `-FilePath` | Target a specific script file |
| `New-AzUpgradeModulePlan` | `-DirectoryPath` | Target all scripts in a folder |
| `New-AzUpgradeModulePlan` | `-FromAzureRmVersion` | Source AzureRM version (use `6.13.1`) |
| `New-AzUpgradeModulePlan` | `-ToAzVersion` | Target Az version (use `latest`) |
| `Invoke-AzUpgradeModulePlan` | `-Plan` | The upgrade plan to execute |
| `Invoke-AzUpgradeModulePlan` | `-FileEditMode` | `SaveChangesToNewFiles` (safe) or `ModifyExistingFiles` (destructive) |

> [!NOTE]
> The **`New-AzUpgradeModulePlan`** cmdlet doesn't execute the plan, it only generates the upgrade steps.

The following example generates a plan for all the scripts in the _`C:\Scripts`_ folder. The
**`OutVariable`** parameter is specified so the results are returned and simultaneously stored in a
variable named **`Plan`**.

```powershell
# Generate an upgrade plan for all the scripts and module files in the specified folder and save it to a variable.
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion latest -DirectoryPath 'C:\Scripts' -OutVariable Plan
```

As shown in the following output, the upgrade plan details the specific file and offset points that
require changes when moving from AzureRM to the Az PowerShell cmdlets.

```Output
Order Location                                                   UpgradeType     PlanResult             Original
----- --------                                                   -----------     ----------             --------
1     compute-create-dockerhost.ps1:59:24                        CmdletParameter ReadyToUpgrade         ExtensionName
2     compute-create-dockerhost.ps1:59:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
3     compute-create-dockerhost.ps1:54:1                         Cmdlet          ReadyToUpgrade         New-AzureRmVM
4     compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter ReadyToUpgrade         ImageName
5     compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          ReadyToUpgrade         New-AzureRmVM
...
```

Each row identifies a cmdlet or parameter that will be renamed from AzureRM to Az format. Items
marked `ReadyToUpgrade` are handled automatically. Items marked with errors require manual review.

Before performing the upgrade, you need to view the results of the plan for problems. The following
example returns a list of scripts and the items in those scripts that will prevent them from being
upgraded automatically.

```powershell
# Filter plan results to only warnings and errors
$Plan | Where-Object PlanResult -ne ReadyToUpgrade | Format-List
```

The items shown in the following output won't be upgraded automatically without manually correcting
the issues first.

```Output
Order                  : 42
UpgradeType            : CmdletParameter
PlanResult             : ErrorParameterNotFound
PlanSeverity           : Error
PlanResultReason       : Parameter was not found in Get-AzResource or it's aliases.
SourceCommand          : CommandReference
SourceCommandParameter : CommandReferenceParameter
Location               : devtestlab-add-marketplace-image-to-lab.ps1:14:74
FullPath               : C:\Scripts\devtestlab-add-marketplace-image-to-lab.ps1
StartOffset            : 556
Original               : ResourceNameEquals
Replacement            :
```

## Run the AzureRM-to-Az upgrade with Invoke-AzUpgradeModulePlan

> [!CAUTION]
> There is no undo operation. Always ensure that you have a backup copy of your PowerShell scripts
> and modules that you're attempting to upgrade.

After you're satisfied with the plan (the `$Plan` variable generated by
`New-AzUpgradeModulePlan` in the previous section), the upgrade is performed with the
[**`Invoke-AzUpgradeModulePlan`**](/powershell/module/az.tools.migration/invoke-azupgrademoduleplan) cmdlet. Specify **`SaveChangesToNewFiles`** for the
**`FileEditMode`** parameter value to prevent changes from being made to your original scripts. When
using this mode, the upgrade is performed by creating a copy of each script targeted with
_`_az_upgraded`_ appended to the filenames.

> [!WARNING]
> The **`Invoke-AzUpgradeModulePlan`** cmdlet is destructive when the
> **`-FileEditMode ModifyExistingFiles`** option is specified! It modifies your scripts and
> functions in place according to the module upgrade plan generated by the
> **`New-AzUpgradeModulePlan`** cmdlet. For the non-destructive option specify
> **`-FileEditMode SaveChangesToNewFiles`** instead.

```powershell
# Execute the automatic upgrade plan and save the results to a variable.
Invoke-AzUpgradeModulePlan -Plan $Plan -FileEditMode SaveChangesToNewFiles -OutVariable Results
```

```Output
Order Location                                                   UpgradeType     UpgradeResult    Original
----- --------                                                   -----------     -------------    --------
1     compute-create-dockerhost.ps1:59:24                        CmdletParameter UpgradeCompleted ExtensionName
2     compute-create-dockerhost.ps1:59:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMExtens...
3     compute-create-dockerhost.ps1:54:1                         Cmdlet          UpgradeCompleted New-AzureRmVM
4     compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter UpgradeCompleted ImageName
5     compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          UpgradeCompleted New-AzureRmVM
...
```

Items marked `UpgradeCompleted` have been successfully renamed from AzureRM to Az format.
Items marked `UnableToUpgrade` require manual correction.

If any errors are returned, you can take a closer look at the error results with the following command:

```powershell
# Filter results to show only errors
$Results | Where-Object UpgradeResult -ne UpgradeCompleted | Format-List
```

```Output
Order                  : 42
UpgradeType            : CmdletParameter
UpgradeResult          : UnableToUpgrade
UpgradeSeverity        : Error
UpgradeResultReason    : Parameter was not found in Get-AzResource or it's aliases.
SourceCommand          : CommandReference
SourceCommandParameter : CommandReferenceParameter
Location               : devtestlab-add-marketplace-image-to-lab.ps1:14:74
FullPath               : C:\Scripts\devtestlab-add-marketplace-image-to-lab.ps1
StartOffset            : 556
Original               : ResourceNameEquals
Replacement            :
```

To verify the upgrade succeeded, check how many items completed successfully:

```powershell
# Count successful upgrades
$Results | Where-Object UpgradeResult -eq UpgradeCompleted | Measure-Object
```

If the count matches the total number of items in your plan, the upgrade completed without errors.

## Limitations

- File I/O operations use default encoding. Unusual file encoding situations may cause problems.
- AzureRM cmdlets passed as arguments to Pester unit test mock statements aren't detected.

## How to report issues

Report feedback and issues about the Az.Tools.Migration PowerShell module via
[a GitHub issue](https://github.com/Azure/azure-powershell-migration/issues) in the
`azure-powershell-migration` repository.

## Next steps

- [Migration Steps](migrate-from-azurerm-to-az.md)
- [Introducing the Az PowerShell module](new-azureps-module-az.md)
- [Changes between AzureRM and Az](migrate-az-1.0.0.md)
- [Install the Az PowerShell module](install-azure-powershell.md)
- [Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)

To learn more about the Az PowerShell module, see the [Azure PowerShell documentation](/powershell/azure/)
