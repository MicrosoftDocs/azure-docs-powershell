---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Config
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Set-AzConfig
---

# Set-AzConfig

## SYNOPSIS

Set or update a configuration value.

## SYNTAX

### \_\_AllParameterSets

```
Set-AzConfig -Key <string> -Value <string> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Set a configuration value using dot notation keys.
If the key already exists, it will be updated.
Unknown keys are rejected unless -Force is specified.

## EXAMPLES

### Set output format

Update the `output.format` setting to `json` so that subsequent commands emit JSON output by default.

```powershell
Set-AzConfig -Key output.format -Value json
```

### Set custom key with force

Use `-Force` to set a key that is not in the documented configuration schema.

```powershell
Set-AzConfig -Key custom.experimental.flag -Value enabled -Force
```

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases:
    - cf
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Force

Allow unknown keys.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
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
HelpMessage: ""
```

### -Key

Configuration key in dot notation.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -Value

Configuration value.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.
Runs the command in a mode that only reports what would happen without performing the actions.
Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases:
    - wi
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

Status string confirming the operation, in the form `Set <key> = <value>`.

## NOTES

Generated help for config.

## RELATED LINKS

- [Online Version]()
