---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmRouteConfig

## SYNOPSIS
Creates a route for a route table.

## SYNTAX

```
New-AzureRmRouteConfig -Name <String> [-AddressPrefix <String>] -NextHopType <String>
 [-NextHopIpAddress <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmRouteConfig cmdlet creates a route for an Azure route table.

## EXAMPLES

### --------------------------  Example 1: Create a route  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$Route = New-AzureRmRouteConfig -Name "route07" -AddressPrefix 10.1.0.0/16 -NextHopType VnetLocal
PS C:\> $Route
Name              : route07
Id                :
Etag              :
ProvisioningState :
AddressPrefix     : 10.1.0.0/16
NextHopType       : VnetLocal
NextHopIpAddress  :
```

The first command creates a route named route07, and then stores it in the $Route variable.
This route forwards packets to the local virtual network.

## PARAMETERS

### -Name
Specifies a name for the route.

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

### -AddressPrefix
Specifies the destination, in Classless Interdomain Routing (CIDR) format, to which the route applies.

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

### -NextHopType
Specifies how this route forwards packets.
Valid values are:

-- Internet. The default Internet gateway provided by Azure.
-- None. If you specify this value, the route does not forward packets.
-- VirtualAppliance. A virtual appliance that you add to your Azure virtual network.
-- VirtualNetworkGateway. An Azure server-to-server virtual private network gateway.
-- VnetLocal. The local virtual network. If you have two subnets, 10.1.0.0/16 and 10.2.0.0/16 in the same virtual network, select a value of VnetLocal for each subnet to forward to the other subnet.

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

### -NextHopIpAddress
Specifies the IP address of a virtual appliance that you add to your Azure virtual network.
This route forwards packets to that address.
Specify this parameter only if you specify a value of VirtualAppliance for the NextHopType parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmRouteConfig]()

[Get-AzureRmRouteConfig]()

[Remove-AzureRmRouteConfig]()

[Set-AzureRmRouteConfig]()

