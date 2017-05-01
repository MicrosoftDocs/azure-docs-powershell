---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmApplicationGatewayFrontendIPConfig

## SYNOPSIS
Creates a front-end IP configuration for an application gateway.

## SYNTAX

### SetByResourceId
```
New-AzureRmApplicationGatewayFrontendIPConfig -Name <String> [-PrivateIPAddress <String>] [-SubnetId <String>]
 [-PublicIPAddressId <String>] [<CommonParameters>]
```

### SetByResource
```
New-AzureRmApplicationGatewayFrontendIPConfig -Name <String> [-PrivateIPAddress <String>] [-Subnet <PSSubnet>]
 [-PublicIPAddress <PSPublicIpAddress>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmApplicationGatewayFrontendIPConfig cmdlet creates a front-end IP configuraton for an Azure application gateway.
An application gateway supports two types of front-end IP configuration:

-- Public IP addresses
 -- Private IP addresses using internal load balancing (ILB).

An application gateway can have at most one public IP address and one private IP address.
The public IP address and private IP address should be added separately as front-end IP addresses.

## EXAMPLES

### --------------------------  Example 1: Create a frontend IP configuration using a public IP resource object  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> $ PublicIP = New-AzureRmPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIP01" -location "West US" -AllocationMethod Dynamic
PS C:\> $FrontEnd = New-AzureRmApplicationGatewayFrontendIPConfig -Name "FrontEndIP01" -PublicIPAddress $PublicIP
```

The first command creates a public IP resource object and stores it in the $PublicIP variable.

### --------------------------  Example 2: Create a static private IP as the frontend IP address  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $FrontEnd = New-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

The first command gets a virtual network named VNet01 that belongs to the resource group named ResourceGroup01, and stores it in the $VNet variable.

### --------------------------  Example 3: Create a dynamic private IP as the frontend IP address  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $FrontEnd = New-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway -Name "FrontendIP03" -Subnet $Subnet
```

The first command gets a virtual network named VNet01 that belongs to the resource group named ResourceGroup01, and stores it in the $VNet variable.

## PARAMETERS

### -Name
Specifies the name of the front-end IP configuration that this cmdlet creates.

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

### -PrivateIPAddress
Specifies the private IP address which this cmdlet associates with the front-end IP address of the application gateway.
This can be specified only if a subnet is specified.
This IP is statically allocated from the subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies the subnet object which this cmdlet associates with the front-end IP address of the application gateway.
If you specify this parameter, it implies that the gateway uses a private IP address.
If PrivateIPAddresss is specified, it should belong to the subnet specified by this parameter.
If PrivateIPAddress is not specified, one of the IP addresses from this subnet is dynamically picked up as the front-end IP address of the application gateway.

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

### -PublicIPAddress
Specifies the public IP address object which this cmdlet associates with the front-end IP address of the application gateway.

```yaml
Type: PSPublicIpAddress
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Specifies the subnet ID which this cmdlet associates with the front-end IP configuration of the application gateway.
If you specify Subnet, it implies that the gateway uses a private IP address.
If PrivateIPAddress is specified, it should belong to the subnet specified by Subnet.
If PrivateIPAddress is not specified, one of the IP addresses from this subnet is dynamically picked up as the front-end IP address of the application gateway.

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

### -PublicIPAddressId
Specifies the public IP address ID which this cmdlet associates with the front-end IP of the application gateway.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSSubnet

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayFrontendIPConfig]()

[Get-AzureRmApplicationGatewayFrontendIPConfig]()

[Remove-AzureRmApplicationGatewayFrontendIPConfig]()

[Set-AzureRmApplicationGatewayFrontendIPConfig]()

