---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Config
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Get-AzConfigInfo
---

# Get-AzConfigInfo

## SYNOPSIS

Display information about valid configuration keys.

## SYNTAX

### __AllParameterSets

```
Get-AzConfigInfo [-KeysOnly] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Show metadata about available configuration keys including their descriptions, default values, and allowed value constraints.
Use -KeysOnly to show only valid key names.

## EXAMPLES

### Display configuration schema

Show every valid configuration key together with its description, default value, and accepted values.

```powershell
Get-AzConfigInfo
```

### Display only key names

List just the valid key identifiers — useful for tab-completion or scripting.

```powershell
Get-AzConfigInfo -KeysOnly
```

## PARAMETERS

### -KeysOnly

Return only valid keys.

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

### System.String

Descriptive text listing available configuration keys, their purpose, and default values. When `-KeysOnly` is supplied, only the key names are emitted (one per line).

## NOTES

Generated help for config.

## RELATED LINKS


- [Online Version]()
