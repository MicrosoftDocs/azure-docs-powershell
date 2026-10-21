---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Network.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Network
ms.date: 09/08/2026
PlatyPS schema version: 2024-05-01
title: Get-AzVirtualNetwork
---

# Get-AzVirtualNetwork

## SYNOPSIS

Get one or more virtual networks.

## SYNTAX

### List (Default)

```
Get-AzVirtualNetwork [-SubscriptionId <string>] [-ResourceGroupName <string>] [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzVirtualNetwork -ResourceGroupName <string> -Name <string> [-SubscriptionId <string>]
 [-ExpandResource <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Retrieves virtual networks.
Supply `-Name` to fetch a single virtual network from a resource group.
Omit `-Name` to list them: scoped to a resource group when `-ResourceGroupName` is supplied, or across the whole subscription when it is not. Listing follows pagination transparently.

## EXAMPLES

### Get a single virtual network

Fetch the virtual network `myvnet` from resource group `myrg`.

```powershell
Get-AzVirtualNetwork -ResourceGroupName myrg -Name myvnet
```

## PARAMETERS

### -ExpandResource

Expand referenced resources, e.g. subnets/ipConfigurations.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The name of the virtual network.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
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

### -ResourceGroupName

The resource group name. Required when retrieving a single virtual network by name; omit it to list every virtual network in the subscription.

```yaml
Type: System.String
DefaultValue: ''
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
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the active profile's subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
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

### Microsoft.Azure.Azclips.Extensions.Network.Models.VirtualNetwork

The matching virtual network, or each virtual network in scope when listing.

## NOTES

Generated help for network.

## RELATED LINKS


- [Online Version]()
