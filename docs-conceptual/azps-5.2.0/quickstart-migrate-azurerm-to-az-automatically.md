---
title: Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module
description: Learn how to automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module.
author: mikefrobbins
ms.service: azure-powershell
ms.topic: quickstart
ms.custom: devx-track-azurepowershell
ms.author: mirobb
ms.date: 12/18/2020
---

# Quickstart: Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module

In this article, you'll learn how to use the Az.Tools.Migration PowerShell module to automatically
upgrade your PowerShell scripts and script modules from AzureRM to the Az PowerShell module. For
additional migration options, see
[Migrate Azure PowerShell from AzureRM to Az](/powershell/azure/migrate-from-azurerm-to-az).

## Requirements

* Update your existing PowerShell scripts to the latest version of the
  [AzureRM PowerShell module (6.13.1)](https://github.com/Azure/azure-powershell/releases/tag/v6.13.1-November2018).
* Install the Az.Tools.Migration PowerShell module.

  ```powershell
  Install-Module -Name Az.Tools.Migration
  ```

## Step 1: Generate an upgrade plan

You use the **`New-AzUpgradeModulePlan`** cmdlet to generate an upgrade plan for migrating your
scripts and modules to the Az PowerShell module. This cmdlet doesn’t make any changes to your
existing scripts. Use the **`FilePath`** parameter for targeting a specific script or the
**`DirectoryPath`** parameter for targeting all scripts in a specific folder.

> [!NOTE]
> The **`New-AzUpgradeModulePlan`** cmdlet doesn't execute the plan, it only generates the upgrade steps.

The following example generates a plan for all the scripts in the _`C:\Scripts`_ folder. The
**`OutVariable`** parameter is specified so the results are returned and simultaneously stored in a
variable named **`Plan`**.

```powershell
# Generate an upgrade plan for all the scripts and module files in the specified folder and save it to a variable.
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion 5.2.0 -DirectoryPath 'C:\Scripts' -OutVariable Plan
```

As shown in the following output, the upgrade plan details the specific file and offset points that
require changes when moving from AzureRM to the Az PowerShell cmdlets.

```Output
Order Location                                                   UpgradeType     PlanResult             Original
----- --------                                                   -----------     ----------             --------
1     compute-create-dockerhost.ps1:59:24                        CmdletParameter ReadyToUpgrade         ExtensionName
2     compute-create-dockerhost.ps1:59:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
3     compute-create-dockerhost.ps1:54:1                         Cmdlet          ReadyToUpgrade         New-AzureRmVM
4     compute-create-dockerhost.ps1:51:1                         Cmdlet          ReadyToUpgrade         Add-AzureRmVM...
5     compute-create-dockerhost.ps1:47:1                         Cmdlet          ReadyToUpgrade         Add-AzureRmVM...
6     compute-create-dockerhost.ps1:46:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
7     compute-create-dockerhost.ps1:45:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
8     compute-create-dockerhost.ps1:44:13                        Cmdlet          ReadyToUpgrade         New-AzureRmVM...
9     compute-create-dockerhost.ps1:40:8                         Cmdlet          ReadyToUpgrade         New-AzureRmNe...
10    compute-create-dockerhost.ps1:36:8                         Cmdlet          ReadyToUpgrade         New-AzureRmNe...
11    compute-create-dockerhost.ps1:31:16                        Cmdlet          ReadyToUpgrade         New-AzureRmNe...
12    compute-create-dockerhost.ps1:26:15                        Cmdlet          ReadyToUpgrade         New-AzureRmNe...
13    compute-create-dockerhost.ps1:22:8                         Cmdlet          ReadyToUpgrade         New-AzureRmPu...
14    compute-create-dockerhost.ps1:18:9                         Cmdlet          ReadyToUpgrade         New-AzureRmVi...
15    compute-create-dockerhost.ps1:15:17                        Cmdlet          ReadyToUpgrade         New-AzureRmVi...
16    compute-create-dockerhost.ps1:12:1                         Cmdlet          ReadyToUpgrade         New-AzureRmRe...
17    compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter ReadyToUpgrade         ImageName
18    compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          ReadyToUpgrade         New-AzureRmVM
19    compute-create-windowsvm-quick.ps1:11:1                    Cmdlet          ReadyToUpgrade         New-AzureRmRe...
20    compute-create-wordpress-mysql.ps1:59:24                   CmdletParameter ReadyToUpgrade         ExtensionName
...
```

Before performing the upgrade, you need to view the results of the plan for problems. The following
example returns a list of scripts and the items in those scripts that will prevent them from being
upgraded automatically.

```powershell
# Filter plan results to only warnings and errors
$Plan | Where-Object PlanResult -ne ReadyToUpgrade | Format-List
```

The items shown in the following output will not be upgraded automatically without manually
correcting the issues first.

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

## Step 2: Perform the upgrade

> [!CAUTION]
> There is no undo operation. Always ensure that you have a backup copy of your PowerShell scripts
> and modules that you're attempting to upgrade.

After you’re satisfied with the plan, the upgrade is performed with the
**`Invoke-AzUpgradeModulePlan`** cmdlet. Specify **`SaveChangesToNewFiles`** for the
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
4     compute-create-dockerhost.ps1:51:1                         Cmdlet          UpgradeCompleted Add-AzureRmVMSshPub...
5     compute-create-dockerhost.ps1:47:1                         Cmdlet          UpgradeCompleted Add-AzureRmVMNetwor...
6     compute-create-dockerhost.ps1:46:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMSource...
7     compute-create-dockerhost.ps1:45:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMOperat...
8     compute-create-dockerhost.ps1:44:13                        Cmdlet          UpgradeCompleted New-AzureRmVMConfig
9     compute-create-dockerhost.ps1:40:8                         Cmdlet          UpgradeCompleted New-AzureRmNetworkI...
10    compute-create-dockerhost.ps1:36:8                         Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
11    compute-create-dockerhost.ps1:31:16                        Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
12    compute-create-dockerhost.ps1:26:15                        Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
13    compute-create-dockerhost.ps1:22:8                         Cmdlet          UpgradeCompleted New-AzureRmPublicIp...
14    compute-create-dockerhost.ps1:18:9                         Cmdlet          UpgradeCompleted New-AzureRmVirtualN...
15    compute-create-dockerhost.ps1:15:17                        Cmdlet          UpgradeCompleted New-AzureRmVirtualN...
16    compute-create-dockerhost.ps1:12:1                         Cmdlet          UpgradeCompleted New-AzureRmResource...
17    compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter UpgradeCompleted ImageName
18    compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          UpgradeCompleted New-AzureRmVM
19    compute-create-windowsvm-quick.ps1:11:1                    Cmdlet          UpgradeCompleted New-AzureRmResource...
20    compute-create-wordpress-mysql.ps1:59:24                   CmdletParameter UpgradeCompleted ExtensionName
...
```

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

## Limitations

* File I/O operations use default encoding. Unusual file encoding situations may cause problems.
* AzureRM cmdlets passed as arguments to Pester unit test mock statements aren't detected.
* Currently, only Az PowerShell module version 5.2.0 is supported as a target.

## How to report issues

Report feedback and issues about the Az.Tools.Migration PowerShell module via
[a GitHub issue](https://github.com/Azure/azure-powershell-migration/issues) in the
`azure-powershell-migration` repository.

## Next steps

To learn more about the Az PowerShell module, see the [Azure PowerShell documentation](/powershell/azure/)
