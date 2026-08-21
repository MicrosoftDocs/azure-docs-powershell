---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Resources
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Get-AzResourceGroup
---

# Get-AzResourceGroup

## SYNOPSIS

Show details of a specific resource group.

## SYNTAX

### List (Default)

```
Get-AzResourceGroup -SubscriptionId <string> [-Profile <string>] [<CommonParameters>]
```

### Get

```
Get-AzResourceGroup -SubscriptionId <string> -Name <string> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Display information about a resource group including its name, location, provisioning state, and resource count.
Specify the resource group name and optionally the subscription ID (defaults to current subscription if not provided).

## EXAMPLES

### Show a resource group

Return the properties of the resource group `myrg` in the specified subscription.

```powershell
Get-AzResourceGroup -SubscriptionId 00000000-0000-0000-0000-000000000000 -Name myrg
```

### List all resource groups in a subscription

List every resource group in the specified subscription. Omit `-Name` to list rather than fetch.

```powershell
Get-AzResourceGroup -SubscriptionId 00000000-0000-0000-0000-000000000000
```

## PARAMETERS

### -Name

The name of the resource group.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: Get
      Position: Named
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
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

### -SubscriptionId

Azure Subscription Id.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: Get
      Position: Named
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
    - Name: List
      Position: Named
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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.ResourceGroup

One `ResourceGroup` object per matching group — a single result when `-Name` is supplied (Get mode), an array of results otherwise (List mode). Includes the name, location, provisioning state, and tags.

## NOTES

Generated help for resources.

## RELATED LINKS

- [Online Version]()
