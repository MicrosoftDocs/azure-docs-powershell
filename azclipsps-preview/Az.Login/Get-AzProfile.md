---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Login.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Login
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Get-AzProfile
---

# Get-AzProfile

## SYNOPSIS

Gets the saved profiles, or the active profile if -Active is specified.

## SYNTAX

### List (Default)

```
Get-AzProfile [<CommonParameters>]
```

### Show

```
Get-AzProfile [-Name] <string> [<CommonParameters>]
```

### ShowActive

```
Get-AzProfile -Active [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Gets the saved profiles, or the active profile if -Active is specified.

## EXAMPLES

### Example 1

Gets the active profile.

```powershell
Get-AzProfile -Active
```

### Example 2

Gets the profile named "prod".

```powershell
Get-AzProfile -Name prod
```

### Example 3

Gets all saved profiles.

```powershell
Get-AzProfile
```

## PARAMETERS

### -Active

Gets the active profile.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: ShowActive
      Position: Named
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Name

Gets the profile with the specified name.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: Show
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

### Microsoft.Azure.Azclips.Extensions.Login.Processors.ProfileSummary

One `ProfileSummary` per configured profile: name, whether it is currently active, tenant ID, subscription ID, cloud, authentication method, and user principal name.

## NOTES

## RELATED LINKS
