---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Login.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Login
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzProfile
---

# Remove-AzProfile

## SYNOPSIS

Removes a saved profile by name.

## SYNTAX

### \_\_AllParameterSets

```
Remove-AzProfile [-Name] <string> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Removes the saved profile with the specified name. If the removed profile was the active profile, the active pointer is cleared.

## EXAMPLES

### Example 1

Removes the profile named "prod".

```powershell
Remove-AzProfile -Name prod
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

### -Name

The name of the saved profile to remove.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: 0
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -WhatIf

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

### System.Void

This cmdlet does not emit an object on the pipeline; it only writes progress and status messages via the Information and Verbose streams.

## NOTES

## RELATED LINKS
