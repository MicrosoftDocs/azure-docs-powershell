---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Config.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Config
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzConfig
---

# Remove-AzConfig

## SYNOPSIS

Delete a configuration value.

## SYNTAX

### \_\_AllParameterSets

```
Remove-AzConfig -Key <string> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Remove a configuration setting by key.
Once deleted, the setting reverts to its default value (if one exists).
Unknown keys are rejected unless -Force is specified.

## EXAMPLES

### Delete a configuration value

Remove the `output.format` setting. The configuration will revert to its default value (if one exists).

```powershell
Remove-AzConfig -Key output.format
```

### Force delete

Use `-Force` to remove an unknown key that is not part of the documented schema.

```powershell
Remove-AzConfig -Key custom.experimental.flag -Force
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

Status string confirming the operation, in the form `Deleted <key>`.

## NOTES

Generated help for config.

## RELATED LINKS

- [Online Version]()
