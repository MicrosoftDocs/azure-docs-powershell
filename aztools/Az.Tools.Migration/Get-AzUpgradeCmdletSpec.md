---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
---

# Get-AzUpgradeCmdletSpec

## SYNOPSIS
Returns a dictionary containing cmdlet specification objects for the specified module.

## SYNTAX

### AzureRM

```
Get-AzUpgradeCmdletSpec [-AzureRM] [<CommonParameters>]
```

### Az

```
Get-AzUpgradeCmdletSpec [-Az] -ModuleVersion <String> [<CommonParameters>]
```

## DESCRIPTION

Returns a dictionary containing cmdlet specification objects for the specified module.

## EXAMPLES

### EXAMPLE 1

Returns the dictionary containing cmdlet specification objects for **AzureRM** 6.13.1.

```powershell
Get-AzUpgradeCmdletSpec -AzureRM
```

## PARAMETERS

### -Az

Import command definitions from Az modules.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Az
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureRM

Import command definitions from **AzureRM** modules.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRM
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleVersion

Specify the version of the module to load command definitions from.

```yaml
Type: System.String
Parameter Sets: Az
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
