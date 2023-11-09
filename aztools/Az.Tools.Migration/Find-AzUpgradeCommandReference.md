---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
---

# Find-AzUpgradeCommandReference

## SYNOPSIS
Searches for **AzureRM** PowerShell command references in the specified file or folder.

## SYNTAX

### ByFileAndModuleSpec

```
Find-AzUpgradeCommandReference -FilePath <String>
 -AzureRmModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>
 [<CommonParameters>]
```

### ByFileAndModuleVersion

```
Find-AzUpgradeCommandReference -FilePath <String> -AzureRmVersion <String> [<CommonParameters>]
```

### ByDirectoryAndModuleSpec

```
Find-AzUpgradeCommandReference -DirectoryPath <String>
 -AzureRmModuleSpec <System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]>
 [<CommonParameters>]
```

### ByDirectoryAndModuleVersion

```
Find-AzUpgradeCommandReference -DirectoryPath <String> -AzureRmVersion <String> [<CommonParameters>]
```

## DESCRIPTION

Searches for **AzureRM** PowerShell command references in the specified file or folder. When
reviewing the specified file or folder, all of the cmdlets used in the files will be analyzed and
compared against known **AzureRM** PowerShell commands. If commands match a known **AzureRM**
cmdlet, then output will be returned that shows the position/offset for each usage.

## EXAMPLES

### EXAMPLE 1

The following example finds **AzureRM** PowerShell command references in the specified file.

```powershell
Find-AzUpgradeCommandReference -FilePath 'C:\Scripts\test.ps1' -AzureRmVersion '6.13.1'
```

### EXAMPLE 2

Find-AzUpgradeCommandReference -DirectoryPath 'C:\Scripts' -AzureRmVersion '6.13.1'

```
The following example finds AzureRM PowerShell command references in the specified directory and subfolders.
```

### EXAMPLE 3

The following example finds **AzureRM** PowerShell command references in the specified directory and
subfolders but with a pre-loaded module specification. This is helpful to avoid reloading the module
specification if the `Find-AzUpgradeCommandReference` command needs to be executed several times.

```powershell
$moduleSpec = Get-AzUpgradeCmdletSpec -AzureRM
Find-AzUpgradeCommandReference -DirectoryPath 'C:\Scripts1' -AzureRmModuleSpec $moduleSpec
Find-AzUpgradeCommandReference -DirectoryPath 'C:\Scripts2' -AzureRmModuleSpec $moduleSpec
Find-AzUpgradeCommandReference -DirectoryPath 'C:\Scripts3' -AzureRmModuleSpec $moduleSpec
```

## PARAMETERS

### -AzureRmModuleSpec

Specifies a dictionary containing cmdlet specification objects, returned from
`Get-AzUpgradeCmdletSpec`.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,CommandDefinition]
Parameter Sets: ByFileAndModuleSpec, ByDirectoryAndModuleSpec
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureRmVersion

Specifies the **AzureRM** module version used in your existing PowerShell file(s) or modules.

```yaml
Type: System.String
Parameter Sets: ByFileAndModuleVersion, ByDirectoryAndModuleVersion
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryPath

Specifies the path to the folder where PowerShell scripts or modules reside.

```yaml
Type: System.String
Parameter Sets: ByDirectoryAndModuleSpec, ByDirectoryAndModuleVersion
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
Parameter Sets: ByFileAndModuleSpec, ByFileAndModuleVersion
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
