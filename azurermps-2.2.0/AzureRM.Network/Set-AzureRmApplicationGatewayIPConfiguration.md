---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmApplicationGatewayIPConfiguration

## SYNOPSIS
Modifies an IP configuration for an application gateway.

## SYNTAX

### SetByResourceId
```
Set-AzureRmApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-SubnetId <String>] [<CommonParameters>]
```

### SetByResource
```
Set-AzureRmApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-Subnet <PSSubnet>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmApplicationGatewayIPConfiguration cmdlet modifies an IP configuration.
An IP configuration contains the subnet in which an application gateway is deployed.

## EXAMPLES

### --------------------------  Example 1: Set the goal state of an IP configuration  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>$VNet = Get-AzureRmVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayIPConfiguration -ApplicationGateway $AppGw
-Name "AppgwSubnet01" -Subnet $Subnets
```

The first command gets the virtual network named VNet01 that belongs to the resource group named ResourceGroup01 and stores it in the $VNet variable.

The forth command sets the IP configuration of the application gateway stored in $AppGw to the subnet configuration stored in $Subnet.

## PARAMETERS

### -ApplicationGateway
Specifies an application gateway object with which this cmdlet associates an IP configuration.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the IP configuration.

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

### -SubnetId
Specifies the subnet ID.
This is the subnet in which the application gateway is deployed.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies the subnet.
This is the subnet in which the application gateway is deployed.

```yaml
Type: PSSubnet
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayIPConfiguration]()

[Get-AzureRmApplicationGatewayIPConfiguration]()

[New-AzureRmApplicationGatewayIPConfiguration]()

[Remove-AzureRmApplicationGatewayIPConfiguration]()

