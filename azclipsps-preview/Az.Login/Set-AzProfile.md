---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Login.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Login
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Set-AzProfile
---

# Set-AzProfile

## SYNOPSIS

Sets the active profile by name.

## SYNTAX

### \_\_AllParameterSets

```
Set-AzProfile [-Name] <string> [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Sets the specified saved profile as the active profile. The change is persisted and does not re-authenticate. Use this to switch the active tenant, subscription, etc. between profiles you have already saved.

## EXAMPLES

### Example 1

Sets the profile named "prod" as the active profile.

```powershell
Set-AzProfile -Name prod
```

## PARAMETERS

### -Name

The name of the saved profile to activate.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Core.Abstractions.Profile

The activated profile object with its tenant ID, subscription ID, cloud, and authentication method after the switch.

## NOTES

## RELATED LINKS
