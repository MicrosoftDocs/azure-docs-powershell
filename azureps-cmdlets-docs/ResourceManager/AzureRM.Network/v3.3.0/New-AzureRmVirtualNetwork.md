---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
ms.assetid: 81D55C43-C9A3-4DA7-A469-A3A7550FE9A4
online version: 
schema: 2.0.0
---

# New-AzureRmVirtualNetwork

## SYNOPSIS
Creates a virtual network.

## SYNTAX

```
New-AzureRmVirtualNetwork -Name <String> -ResourceGroupName <String> -Location <String>
 -AddressPrefix <System.Collections.Generic.List`1[System.String]>
 [-DnsServer <System.Collections.Generic.List`1[System.String]>]
 [-Subnet <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSSubnet]>]
 [-Tag <Hashtable>] [-Force] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmVirtualNetwork** cmdlet creates an Azure virtual network.

## EXAMPLES

### Example 1: Create a virtual network based on two subnets
```
PS C:\> New-AzureRmResourceGroup -Name "ResourceGroup03" -Location centralus
PS C:\> $FrontendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -AddressPrefix "10.0.1.0/24"
PS C:\> $BackendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "BackendSubnet" -AddressPrefix "10.0.2.0/24"
PS C:\> New-AzureRmVirtualNetwork -Name "MyVirtualNetwork" -ResourceGroupName "ResourceGroup03" -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $FrontendSubnet,$BackendSubnet
```

The first command creates a resource group named ResourceGroup03 in the centralus region by using the **New-AzureRmResourceGroup** cmdlet.

The second command creates a subnet called FrontendSubnet by using the **New-AzureRmVirtualNetworkSubnetConfig** cmdlet. 
This is an in-memory representations of the subnet. 
The command stores it in the $FrontendSubnet variable. 

The third command creates a subnet called BackendSubnet, and stores it in the $BackendSubnet variable. 

The final command creates a virtual network that uses the CIDR 10.0.0.0/16 as the address prefix and the two subnets created in the previous commands. 
    
### Example 2: Create a virtual network with DNS settings 
```
PS C:\> New-AzureRmResourceGroup -Name "ResourceGroup03" -Location centralus
PS C:\> $FrontendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -AddressPrefix "10.0.1.0/24"
PS C:\> $BackendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "BackendSubnet" -AddressPrefix "10.0.2.0/24"
PS C:\> New-AzureRmVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName "ResourceGroup03" -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $FrontendSubnet,$BackendSubnet -DnsServer 10.0.1.5,10.0.1.6
```

The first command creates a resource group named ResourceGroup03 in the centralus region by using the **New-AzureRmResourceGroup** cmdlet.

The second command creates a subnet called FrontendSubnet, and stores it in the $FrontendSubnet variable.

The third command creates a subnet called BackendSubnet, and stores it in the $BackendSubnet variable. 

The final command creates a virtual network that uses the CIDR 10.0.0.0/16 as the address prefix and the two subnets created in the previous commands. 
The command specifies DNS servers. 
If no DNS servers are specified on a virtual network and there are no DNS servers on the interfaces, the default Azure DNS servers are used for DNS resolution.

### Example 3: Create a virtual network with subnets that reference a network security group
```
PS C:\> New-AzureRmResourceGroup -Name "ResourceGroup03" -Location centralus
PS C:\> $RdpRule = New-AzureRmNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
PS C:\> $NetworkSecurityGroup = New-AzureRmNetworkSecurityGroup -ResourceGroupName "ResourceGroup03" -Location centralus -Name "NSG-FrontEnd" -SecurityRules $RdpRule
PS C:\> $FrontendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -AddressPrefix "10.0.1.0/24" -NetworkSecurityGroup $NetworkSecurityGroup
PS C:\> $BackendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "BackendSubnet" -AddressPrefix "10.0.2.0/24" -NetworkSecurityGroup $NetworkSecurityGroup
PS C:\> New-AzureRmVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName "ResourceGroup03" -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $FrontendSubnet,$BackendSubnet
```

The first command creates a resource group named ResourceGroup03 in the centralus region by using the **New-AzureRmResourceGroup** cmdlet.

The second command creates a rule that allows inbound RDP access by using the **New-AzureRmNetworkSecurityRuleConfig** cmdlet.
The command stores the rule in the $RdpRule variable.

The third command creates a network security group that includes the rule in $RdpRule by using the **New-AzureRmNetworkSecurityGroup** cmdlet.
The command stores the group in the $NetworkSecurityGroup variable.

The fourth command creates a subnet called FrontendSubnet, and stores it in the $FrontendSubnet variable.

The fifth command creates a subnet called BackendSubnet, and stores it in the $BackendSubnet variable. 

The final command creates a virtual network that uses the CIDR 10.0.0.0/16 as the address prefix and the two subnets created in the previous commands. 
The subnets both reference the security group stored in $NetworkSecurityGroup.

## PARAMETERS

### -AddressPrefix
Specifies a range of IP addresses for a virtual network.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsServer
Specifies the DNS server for a subnet.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

### -Location
Specifies the region for the virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual network that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group to contain the virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subnet
Specifies a list of subnets to associate with the virtual network.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSSubnet]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies a dictionary of tags to associate with the network interface.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmVirtualNetwork](./Get-AzureRmVirtualNetwork.md)

[New-AzureRmResourceGroup](./New-AzureRmResourceGroup.md)

[New-AzureRmNetworkSecurityGroup](./New-AzureRmNetworkSecurityGroup.md)

[New-AzureRmNetworkSecurityRuleConfig](./New-AzureRmNetworkSecurityRuleConfig.md)

[New-AzureRmVirtualNetworkSubnetConfig](./New-AzureRmVirtualNetworkSubnetConfig.md)

[Remove-AzureRmVirtualNetwork](./Remove-AzureRmVirtualNetwork.md)

[Set-AzureRmVirtualNetwork](./Set-AzureRmVirtualNetwork.md)
