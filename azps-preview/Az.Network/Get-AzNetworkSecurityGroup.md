---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Network.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Network
ms.date: 10/22/2026
PlatyPS schema version: 2024-05-01
title: Get-AzNetworkSecurityGroup
---

# Get-AzNetworkSecurityGroup

## SYNOPSIS

Get a network security group, or list the network security groups in a resource group or subscription.

## SYNTAX

### List (Default)

```
Get-AzNetworkSecurityGroup [-SubscriptionId <string>] [-ResourceGroupName <string>] [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzNetworkSecurityGroup -ResourceGroupName <string> -Name <string> [-SubscriptionId <string>]
 [-ExpandResource <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Gets a network security group by name, or lists the network security groups in a resource group or, when `-ResourceGroupName` is omitted, in the whole subscription.

## EXAMPLES

### Get a network security group

Show the network security group `mynsg` in resource group `myrg`.

```powershell
Get-AzNetworkSecurityGroup -ResourceGroupName myrg -Name mynsg
```

### Expand the associated network interfaces

```powershell
Get-AzNetworkSecurityGroup -ResourceGroupName myrg -Name mynsg -ExpandResource networkInterfaces
```

### List the network security groups in a resource group

```powershell
Get-AzNetworkSecurityGroup -ResourceGroupName myrg
```

### List every network security group in the subscription

```powershell
Get-AzNetworkSecurityGroup
```

## PARAMETERS

### -ExpandResource

Expands referenced resources in the response, e.g. `networkInterfaces` or `subnets`.

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

Name of the network security group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceName
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

Azure profile to target, e.g. `latest`.

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

Name of the resource group that contains the network security group.

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

ID of the subscription that contains the network security group. Defaults to the subscription of the current context.

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

### Microsoft.Azure.Azclips.Extensions.Network.Models.NetworkSecurityGroup

The requested network security group, or every network security group in the resource group or subscription when `-Name` is omitted.

## NOTES

Generated help for network.

## RELATED LINKS


- [Online Version]()
