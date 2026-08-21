---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Config
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Get-AzConfig
---

# Get-AzConfig

## SYNOPSIS

Retrieve a configuration value.

## SYNTAX

### __AllParameterSets

```
Get-AzConfig -Key <string> [-AsJson] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Get the current value of a configuration setting by key.
Configuration keys use dot notation (e.g., output.format, core.debug).
If the key is not found, an error is displayed.

## EXAMPLES

### Get a configuration value

Return the current value of the `output.format` configuration setting.

```powershell
Get-AzConfig -Key output.format
```

### Get output as JSON

Return the value formatted as JSON instead of plain text. Useful for piping into `ConvertFrom-Json` in scripts.

```powershell
Get-AzConfig -Key output.format -AsJson
```

## PARAMETERS

### -AsJson

Return the configuration value as a JSON string instead of the default plain text. Useful when piping into `ConvertFrom-Json` or capturing structured output for downstream scripts.

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

### -Key

Configuration key in dot notation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
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

### System.String

The current value of the configuration setting identified by `-Key`. Returned as plain text by default, or as a JSON string when `-AsJson` is supplied (pipe into `ConvertFrom-Json` for structured downstream processing).

## NOTES

Generated help for config.

## RELATED LINKS


- [Online Version]()
