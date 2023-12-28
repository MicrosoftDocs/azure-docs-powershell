---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
original_content_git_url: https://github.com/Azure/azure-powershell-migration/blob/main/powershell-module/help/New-AzUpgradeModulePlan.md
---

# New-AzUpgradeModulePlan

## SYNOPSIS
Generates a new upgrade plan for migrating to the **Az** PowerShell module.

## SYNTAX

### FromReferences

```
New-AzUpgradeModulePlan -AzureRmCmdReference <CommandReference[]> -ToAzVersion <String>
 [-AzureRmModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzAliasMappingSpec <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [<CommonParameters>]
```

### FromNewSearchByDirectory

```
New-AzUpgradeModulePlan -FromAzureRmVersion <String> -DirectoryPath <String> -ToAzVersion <String>
 [-AzureRmModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzAliasMappingSpec <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [<CommonParameters>]
```

### FromNewSearchByFile

```
New-AzUpgradeModulePlan -FromAzureRmVersion <String> -FilePath <String> -ToAzVersion <String>
 [-AzureRmModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>]
 [-AzAliasMappingSpec <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [<CommonParameters>]
```

## DESCRIPTION

Generates a new upgrade plan for migrating to the **Az** PowerShell module. The upgrade plan details
the specific file/offset points that require changes when moving from **AzureRM** commands to Az
commands.

## EXAMPLES

### EXAMPLE 1

The following example generates a new **Az** module upgrade plan for the script file
`C:\Scripts\my-azure-script.ps1`.

```powershell
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion latest -FilePath 'C:\Scripts\my-azure-script.ps1'
```

### EXAMPLE 2

The following example generates a new **Az** module upgrade plan for the script and module files
located under `C:\Scripts`.

```powershell
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion latest -DirectoryPath 'C:\Scripts'
```

### EXAMPLE 3

The following example generates a new **Az** module upgrade plan for the script and module files
under `C:\Scripts`.

```powershell
$references = Find-AzUpgradeCommandReference -DirectoryPath 'C:\Scripts' -AzureRmVersion '6.13.1'
New-AzUpgradeModulePlan -ToAzVersion latest -AzureRmCmdReference $references
```

### EXAMPLE 4

The following example generates a new **Az** module upgrade plan for the script and module files
under several directories. Module specs are pre-loaded here to avoid re-loading the spec each time a
plan is generated.

```powershell
# pre-load specifications

$armSpec = Get-AzUpgradeCmdletSpec -AzureRM
$azSpec = Get-AzUpgradeCmdletSpec -Az -ModuleVersion latest
$azAliases = Get-AzUpgradeAliasSpec -ModuleVersion latest

# execute a batch of module upgrades

$plan1 = New-AzUpgradeModulePlan -DirectoryPath 'C:\Scripts1' -FromAzureRmVersion '6.13.1' -ToAzVersion latest -AzureRmModuleSpec $armSpec -AzModuleSpec $azSpec -AzAliasMappingSpec $azAliases
$plan2 = New-AzUpgradeModulePlan -DirectoryPath 'C:\Scripts2' -FromAzureRmVersion '6.13.1' -ToAzVersion latest -AzureRmModuleSpec $armSpec -AzModuleSpec $azSpec -AzAliasMappingSpec $azAliases
$plan3 = New-AzUpgradeModulePlan -DirectoryPath 'C:\Scripts3' -FromAzureRmVersion '6.13.1' -ToAzVersion latest -AzureRmModuleSpec $armSpec -AzModuleSpec $azSpec -AzAliasMappingSpec $azAliases
```

## PARAMETERS

### -AzAliasMappingSpec

Specifies an optional parameter to provide a pre-loaded Az cmdlet alias mapping table, returned from
`Get-AzUpgradeAliasSpec`.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzModuleSpec

Specifies an optional parameter to provide a pre-loaded **Az** module spec, returned from
`Get-AzUpgradeCmdletSpec`.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureRmCmdReference

Specifies the **AzureRM** command references output from the `Find-AzUpgradeCommandReference`
cmdlet.

```yaml
Type: CommandReference[]
Parameter Sets: FromReferences
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureRmModuleSpec

Specifies an optional parameter to provide a pre-loaded **AzureRM** module spec, returned from
`Get-AzUpgradeCmdletSpec`.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryPath

Specifies the path to a folder where PowerShell scripts or modules reside.

```yaml
Type: System.String
Parameter Sets: FromNewSearchByDirectory
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Specifies the path to a single PowerShell file.

```yaml
Type: System.String
Parameter Sets: FromNewSearchByFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromAzureRmVersion

Specifies the **AzureRM** module version used in your existing PowerShell scripts(s) or modules.

```yaml
Type: System.String
Parameter Sets: FromNewSearchByDirectory, FromNewSearchByFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToAzVersion

Specifies the **Az** module version to upgrade to. Currently, only Az version 10.3 is supported.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
