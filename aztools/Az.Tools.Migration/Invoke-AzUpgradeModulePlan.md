﻿---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
original_content_git_url: https://github.com/Azure/azure-powershell-migration/blob/main/powershell-module/help/Invoke-AzUpgradeModulePlan.md
---

# Invoke-AzUpgradeModulePlan

## SYNOPSIS
Invokes the specified module upgrade plan.

## SYNTAX

```
Invoke-AzUpgradeModulePlan [-Plan] <UpgradePlan[]> [-FileEditMode] <EditMode> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Invokes the specified module upgrade plan.

> [!IMPORTANT]
> This step is destructive if the **FileEditMode** parameter is set to `ModifyExistingFiles`. This
> mode makes file edits in place according to the module upgrade plan. There is no undo operation.
> Always ensure that you have a backup copy of the target PowerShell script or module.

To save the upgraded script contents into new files, leaving the originals unmodified, specify
`SaveChangesToNewFiles` with the **FileEditMode** parameter.

The upgrade plan is generated by running the `New-AzUpgradeModulePlan` cmdlet.

## EXAMPLES

### EXAMPLE 1

The following example invokes the upgrade plan for a PowerShell module named **myModule** and saves
the updated file contents into new files, leaving the original files unmodified.

```powershell
# step 1: generate a plan and save it to a variable.
$plan = New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion latest -DirectoryPath 'C:\Scripts\myModule'

# step 2: write the plan to the console to review the upgrade steps, warnings, and errors.
$plan

# step 3: run the automatic upgrade plan (saving updated scripts to new files) and collects the results in a variable.
$results = Invoke-AzUpgradeModulePlan -Plan $Plan -FileEditMode SaveChangesToNewFiles

# step 4: write the upgrade results to the console to review the result for each upgrade step.
$results
```

### EXAMPLE 2

The following example invokes the upgrade plan for a PowerShell module named **myModule** and
modifies the existing files in place.

```powershell
# step 1: generate a plan and save it to a variable.
$plan = New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion latest -DirectoryPath 'C:\Scripts\myModule'

# step 2: write the plan to the console to review the upgrade steps, warnings, and errors.
$plan

# step 3: run the automatic upgrade plan (modifying the files in place) and collects the results in a variable.
$results = Invoke-AzUpgradeModulePlan -Plan $Plan -FileEditMode ModifyExistingFiles

# step 4: write the upgrade results to the console to review the result for each upgrade step.
$results
```

## PARAMETERS

### -FileEditMode

Specifies the file edit mode to determine if the upgrade plan should be executed in place, modifies
existing files, or if changes should be saved to new files. Specify `ModifyExistingFiles` to modify
your script files in place, or `SaveChangesToNewFiles` to save new PowerShell files, leaving your
existing files unmodified.

```yaml
Type: EditMode
Parameter Sets: (All)
Aliases:
Accepted values: ModifyExistingFiles, SaveChangesToNewFiles

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Plan

Specifies the upgrade plan steps to execute. This is generated from `New-AzUpgradeModulePlan`.

```yaml
Type: UpgradePlan[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
