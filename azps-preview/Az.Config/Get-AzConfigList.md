---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Config
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Get-AzConfigList
---

# Get-AzConfigList

## SYNOPSIS

List all configuration settings.

## SYNTAX

### __AllParameterSets

```
Get-AzConfigList [-IncludeDefaults] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Display all current configuration values.
By default, only explicitly-set values are shown.
Use `-IncludeDefaults` to include default values.
Each configuration entry is emitted as a structured object.

## EXAMPLES

### List all configuration

Display every explicitly-set configuration value.

```powershell
Get-AzConfigList
```

### List with defaults

Include default values for keys that have not been explicitly set.

```powershell
Get-AzConfigList -IncludeDefaults
```

## PARAMETERS

### -IncludeDefaults

Include keys that have not been explicitly set, showing their built-in default values. Without this switch only keys with user-assigned values are listed.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Config.Models.ConfigEntry

One object per configured entry. Add `-IncludeDefaults` to also emit keys that have not been explicitly set.

## NOTES

Generated help for config.

## RELATED LINKS


- [Online Version]()
