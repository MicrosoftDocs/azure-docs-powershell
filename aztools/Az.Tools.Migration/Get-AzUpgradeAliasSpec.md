---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
original_content_git_url: https://github.com/Azure/azure-powershell-migration/blob/main/powershell-module/help/Get-AzUpgradeAliasSpec.md
---

# Get-AzUpgradeAliasSpec

## SYNOPSIS
Returns a dictionary containing cmdlet alias mappings for the specified **Az** module version.

## SYNTAX

```
Get-AzUpgradeAliasSpec [-ModuleVersion] <String> [<CommonParameters>]
```

## DESCRIPTION

Returns a dictionary containing cmdlet alias mappings for the specified **Az** module version.

## EXAMPLES

### EXAMPLE 1

Returns the cmdlet alias mappings table for latest Az version.

```powershell
Get-AzUpgradeAliasSpec -ModuleVersion latest
```

## PARAMETERS

### -ModuleVersion

Specify the version of the module to import command aliases from.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
