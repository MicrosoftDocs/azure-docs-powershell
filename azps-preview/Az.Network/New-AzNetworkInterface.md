---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Network.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Network
ms.date: 10/05/2026
PlatyPS schema version: 2024-05-01
title: New-AzNetworkInterface
---

# New-AzNetworkInterface

## SYNOPSIS

Create a network interface.

## SYNTAX

### __AllParameterSets

```
New-AzNetworkInterface -Name <string> -Location <string> -ResourceGroupName <string>
 -SubnetId <string> [-SubscriptionId <string>] [-PublicIpAddressId <string>]
 [-NetworkSecurityGroupId <string>] [-PrivateIpAddress <string>] [-IpConfigurationName <string>]
 [-DnsServer <string[]>] [-InternalDnsNameLabel <string>] [-EnableAcceleratedNetworking]
 [-EnableIPForwarding] [-EdgeZone <string>] [-Tag <hashtable>] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates a network interface with a single IP configuration in an existing subnet.
`-PublicIpAddressId` and `-NetworkSecurityGroupId` associate an existing public IP address and network security group; each takes a resource id, or the name of a resource in `-ResourceGroupName`.

The IP configuration is named `ipconfig1` unless `-IpConfigurationName` is supplied. Its private IP address is allocated dynamically unless `-PrivateIpAddress` is supplied, in which case the allocation is `Static`.

## EXAMPLES

### Create a network interface in a subnet

Create the network interface `mynic` in the first subnet of the virtual network `myvnet`.

```powershell
$vnet = Get-AzVirtualNetwork -ResourceGroupName myrg -Name myvnet
New-AzNetworkInterface -ResourceGroupName myrg -Name mynic -Location eastus -SubnetId $vnet.Properties.Subnets[0].Id
```

### Create a network interface with a public IP address and a network security group

`-NetworkSecurityGroupId` takes the name of a network security group in `-ResourceGroupName` as well as a resource id.

```powershell
$vnet = Get-AzVirtualNetwork -ResourceGroupName myrg -Name myvnet
$pip = Get-AzPublicIpAddress -ResourceGroupName myrg -Name mypip
New-AzNetworkInterface -ResourceGroupName myrg -Name mynic -Location eastus -SubnetId $vnet.Properties.Subnets[0].Id `
    -PublicIpAddressId $pip.Id -NetworkSecurityGroupId mynsg
```

### Create a network interface with a static private IP address and accelerated networking

```powershell
$subnetId = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Network/virtualNetworks/myvnet/subnets/default'
New-AzNetworkInterface -ResourceGroupName myrg -Name mynic -Location eastus -SubnetId $subnetId `
    -PrivateIpAddress 10.0.0.10 -EnableAcceleratedNetworking `
    -DnsServer 10.0.0.4, 10.0.0.5 -Tag @{ owner = 'team-a' }
```

## PARAMETERS

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

### -DnsServer

DNS server IP addresses for the network interface. When omitted, the network interface uses the DNS servers of the virtual network.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DnsServers
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

Name of the edge zone (extended location) to create the network interface in.

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

### -EnableAcceleratedNetworking

Enable accelerated networking on the network interface.

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

### -EnableIPForwarding

Enable IP forwarding on the network interface.

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

### -InternalDnsNameLabel

Relative DNS name for the network interface, used for internal communication between virtual machines in the same virtual network.

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

### -IpConfigurationName

Name of the IP configuration. Defaults to `ipconfig1`.

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

### -Location

Location of the network interface, e.g. `eastus`. It must match the location of the virtual network that contains the subnet.

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

Name of the network interface.

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

### -NetworkSecurityGroupId

Resource id of an existing network security group to associate with the network interface. A bare name resolves to a network security group in `-ResourceGroupName`.

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

### -PrivateIpAddress

Static private IP address from the address range of the subnet. When omitted, a private IP address is allocated dynamically.

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

### -PublicIpAddressId

Resource id of an existing public IP address to associate with the IP configuration. A bare name resolves to a public IP address in `-ResourceGroupName`.

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

Name of the resource group to create the network interface in.

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

### -SubnetId

Resource id of the existing subnet that the IP configuration is attached to.

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

### -SubscriptionId

ID of the subscription to create the network interface in. Defaults to the subscription of the current context.

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

Resource tags supplied as a hashtable, e.g. @{ owner = 'team-a' }.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Network.Models.NetworkInterface

The network interface that was created, including its IP configuration, the allocated private IP address, and its provisioning state.

## NOTES

Generated help for network.

## RELATED LINKS


- [Online Version]()

