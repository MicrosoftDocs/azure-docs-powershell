---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Config
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Get-AzConfig
---

# Get-AzConfig

## SYNOPSIS

Retrieve a configuration value.

## SYNTAX

### __AllParameterSets

```
Get-AzConfig -Key <string> [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Get the current value of a configuration setting by key.
Configuration keys use dot notation (e.g., core.logging.level, defaults.location).
If the key is not found, an error is displayed.

## EXAMPLES

### Get a configuration value

Return the current global logging level.

```powershell
Get-AzConfig -Key core.logging.level
```

### Get a configuration section

Return structured entries whose keys are relative to the requested section.

```powershell
Get-AzConfig -Key core
```

## PARAMETERS

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

### Microsoft.Azure.Azclips.Extensions.Config.Models.ConfigEntry

One configuration entry for an exact key, or configuration entries with relative keys when `-Key` identifies a section.

## NOTES

Generated help for config.

## RELATED LINKS


- [Online Version]()
