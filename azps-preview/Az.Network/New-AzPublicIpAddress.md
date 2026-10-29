---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Network.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Network
ms.date: 10/27/2026
PlatyPS schema version: 2024-05-01
title: New-AzPublicIpAddress
---

# New-AzPublicIpAddress

## SYNOPSIS

Create a public IP address.

## SYNTAX

### __AllParameterSets

```
New-AzPublicIpAddress -Name <string> -Location <string> -ResourceGroupName <string>
 [-SubscriptionId <string>] [-Sku <string>] [-Tier <string>] [-AllocationMethod <string>]
 [-IpAddressVersion <string>] [-DomainNameLabel <string>] [-DomainNameLabelScope <string>]
 [-ReverseFqdn <string>] [-IdleTimeoutInMinutes <int>] [-IpAddress <string>] [-IpTag <hashtable>]
 [-PublicIpPrefix <string>] [-DdosProtectionMode <string>] [-DdosProtectionPlanId <string>]
 [-DdosCustomPolicyId <string>] [-Zone <string[]>] [-EdgeZone <string>] [-Tag <hashtable>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates a public IP address that gives internet-facing connectivity to resources such as load balancers, application gateways, VPN gateways, and virtual machine network interfaces.

`-Sku` defaults to `Standard`, `-IpAddressVersion` defaults to `IPv4`, and `-IdleTimeoutInMinutes` defaults to `4`.
When `-AllocationMethod` is omitted it is inferred from the SKU: `Static` for `Standard` and `StandardV2`, `Dynamic` for `Basic`.
Standard SKU addresses are zone-redundant by default; use `-Zone` to pin the address to specific availability zones.

## EXAMPLES

### Create a Standard public IP address

Create a zone-redundant Standard static IPv4 address.

```powershell
New-AzPublicIpAddress -ResourceGroupName myrg -Name mypip -Location eastus -Zone 1, 2, 3
```

### Create an address with a DNS name and tags

```powershell
New-AzPublicIpAddress -ResourceGroupName myrg -Name mypip -Location eastus `
    -DomainNameLabel mylabel -Tag @{ owner = 'team-a'; costCenter = '42' }
```

### Create a Basic dynamic IPv6 address

```powershell
New-AzPublicIpAddress -ResourceGroupName myrg -Name mypip -Location eastus `
    -Sku Basic -IpAddressVersion IPv6 -AllocationMethod Dynamic
```

### Create an address with DDoS protection and an IP tag

```powershell
New-AzPublicIpAddress -ResourceGroupName myrg -Name mypip -Location eastus `
    -DdosProtectionMode Enabled -DdosProtectionPlanId myplan `
    -IpTag @{ FirstPartyUsage = '/Sql' }
```

## PARAMETERS

### -AllocationMethod

IP address allocation method. Defaults to `Static` for the `Standard` and `StandardV2` SKUs and `Dynamic` for the `Basic` SKU.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
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
HelpMessage: ''
```

### -DdosCustomPolicyId

Name or resource ID of the DDoS custom policy associated with the public IP address.

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

### -DdosProtectionMode

DDoS protection mode of the public IP address. Accepted values are `Enabled`, `Disabled` and `VirtualNetworkInherited`.

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

### -DdosProtectionPlanId

Name or resource ID of the DDoS protection plan associated with the public IP address.

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

### -DomainNameLabel

DNS name label. The concatenation of the label and the regional DNS zone forms the fully qualified domain name of the public IP address.

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

### -DomainNameLabelScope

Scope of the domain name label. Accepted values are `NoReuse`, `ResourceGroupReuse`, `SubscriptionReuse` and `TenantReuse`.

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

### -EdgeZone

Name of the edge zone (extended location) to create the public IP address in.

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

### -IdleTimeoutInMinutes

Idle timeout of the public IP address, in minutes. Defaults to 4.

```yaml
Type: System.Int32
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

### -IpAddress

The IP address associated with the public IP address resource.

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

### -IpAddressVersion

IP address version. Accepted values are `IPv4` and `IPv6`. Defaults to `IPv4`.

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

### -IpTag

IP tags to apply, as a hashtable of tag type to tag value, e.g. `@{ FirstPartyUsage = '/Sql' }`.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases:
- IpTags
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

### -Location

Azure region in which to create the public IP address.

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

### -Name

Name of the public IP address.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceName
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

### -PublicIpPrefix

Name or resource ID of the public IP prefix to allocate the address from.

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

Name of the resource group that contains the public IP address.

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

### -ReverseFqdn

Reverse fully qualified domain name. The address resolves to this FQDN on a reverse DNS lookup.

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

### -Sku

SKU of the public IP address. Accepted values are `Basic`, `Standard` and `StandardV2`. Defaults to `Standard`.

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

### -SubscriptionId

ID of the subscription that contains the public IP address. Defaults to the subscription of the current context.

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

### -Tag

Resource tags, as a hashtable of tag name to tag value.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Tags
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

### -Tier

Tier of the public IP address SKU. Accepted values are `Regional` and `Global`.

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

### -WhatIf

Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
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
HelpMessage: ''
```

### -Zone

Availability zones to allocate the public IP address in. Only supported for the Standard SKUs.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Zones
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

### Microsoft.Azure.Azclips.Extensions.Network.Models.PublicIpAddress

The public IP address that was created.

## NOTES

Generated help for network.

## RELATED LINKS
