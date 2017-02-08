---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
ms.assetid: D1D51DEF-05DE-45C4-9013-A02A5B248EAC
online version: 
schema: 2.0.0
---

# Set-AzureRmVirtualNetworkSubnetConfig

## SYNOPSIS
Configures the goal state for a subnet configuration in a virtual network.

## SYNTAX

### SetByResource (Default)
```
Set-AzureRmVirtualNetworkSubnetConfig -Name <String> -VirtualNetwork <PSVirtualNetwork> -AddressPrefix <String>
 [-NetworkSecurityGroup <PSNetworkSecurityGroup>] [-RouteTable <PSRouteTable>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### SetByResourceId
```
Set-AzureRmVirtualNetworkSubnetConfig -Name <String> -VirtualNetwork <PSVirtualNetwork> -AddressPrefix <String>
 [-NetworkSecurityGroupId <String>] [-RouteTableId <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmVirtualNetworkSubnetConfig** cmdlet configures the goal state for a subnet configuration in an Azure virtual network.

## EXAMPLES

### Example 1: Modify the address prefix of a subnet

```
PS C:\> $VirtualNetwork = Get-AzureRmVirtualNetwork -Name "MyVirtualNetwork" -ResourceGroupName "ResourceGroup03"
PS C:\> Set-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -VirtualNetwork $VirtualNetwork -AddressPrefix "10.0.3.0/23"
PS C:\> $VirtualNetwork | Set-AzureRmVirtualNetwork    
```

The first command gets a virtual network named MyVirtualNetwork by using the **Get-AzureRmVirtualNetwork** cmdlet. 
The command stores this value in the $VirtualNetwork variable.

The second command modifies the *AddressPrefix* of on of the virtual network's subnets. 
This changes only the local representation of the virtual network. 

The final command persists the change to the virtual network to the service side by using the **Set-AzureRmVirtualNetwork** cmdlet. 

### Example 2: Add a network security group to a subnet
```
PS C:\> $VirtualNetwork = Get-AzureRmVirtualNetwork -Name "MyVirtualNetwork" -ResourceGroupName "ResourceGroup03"
PS C:\> $RdpRule = New-AzureRmNetworkSecurityRuleConfig -Name "rdp-rule" -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
PS C:\> $NetworkSecurityGroup = New-AzureRmNetworkSecurityGroup -ResourceGroupName "ResourceGroup03" -Location centralus -Name "NSG-FrontEnd" -SecurityRules $RdpRule
PS C:\> Set-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -VirtualNetwork $VirtualNetwork -AddressPrefix "10.0.1.0/24" -NetworkSecurityGroup $NetworkSecurityGroup
PS C:\> $VirtualNetwork | Set-AzureRmVirtualNetwork
```

The first command gets a virtual network named MyVirtualNetwork and stores it in the $VirtualNetwork variable.

The second command creates a rule that allows RDP traffic by using the **New-AzureRmNetworkSecurityRuleConfig** cmdlet. 
The command stores the rule in the $RdpRule variable. 

The third command creates a network security group named NSG-FrontEnd that includes the rule in $RdpRule by using the **New-AzureRmNetworkSecurityRuleConfig** cmdlet. 
The command stores the group in the $NetworkSecurityGroup variable. 

The fourth command modifies the local representation stored in $VirtualNetwork so that the frontend subnet points to the security group in $NetworkSecurityGroup.

The final command persists the change to the virtual network to the service side by using the **Set-AzureRmVirtualNetwork** cmdlet. 

## PARAMETERS

### -AddressPrefix
Specifies a range of IP addresses for a subnet configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a subnet configuration that this cmdlet configures.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSecurityGroup
Specifies a **NetworkSecurityGroup** object.

```yaml
Type: PSNetworkSecurityGroup
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkSecurityGroupId
Specifies the ID of a network security group.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteTable
Specifies the route table object that is associated with the network security group.

```yaml
Type: PSRouteTable
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteTableId
Specifies the ID of the route table object that is associated with the network security group.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies the **VirtualNetwork** object that contains the subnet configuration.

```yaml
Type: PSVirtualNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmVirtualNetworkSubnetConfig](./Add-AzureRmVirtualNetworkSubnetConfig.md)

[Get-AzureRmVirtualNetwork](./Get-AzureRmVirtualNetwork.md)

[Get-AzureRmVirtualNetworkSubnetConfig](./Get-AzureRmVirtualNetworkSubnetConfig.md)

[New-AzureRmVirtualNetworkSubnetConfig](./New-AzureRmVirtualNetworkSubnetConfig.md)

[New-AzureRmNetworkSecurityRuleConfig](./New-AzureRmNetworkSecurityRuleConfig.md)

[Remove-AzureRmVirtualNetworkSubnetConfig](./Remove-AzureRmVirtualNetworkSubnetConfig.md)

[Set-AzureRmVirtualNetwork](./Set-AzureRmVirtualNetwork.md)

