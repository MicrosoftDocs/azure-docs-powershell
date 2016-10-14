---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureRouteConfig.md
schema: 2.0.0
---

# Add-AzureRouteConfig

## SYNOPSIS
Adds a route to a route table.

## SYNTAX

```
Add-AzureRouteConfig -Name <String> -RouteTable <PSRouteTable> [-AddressPrefix <String>] -NextHopType <String>
 [-NextHopIpAddress <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRouteConfig** cmdlet adds a route to an Azure route table.

## EXAMPLES

### Example 1: Add a route to a route table
```
PS C:\>$RouteTable = Get-AzureRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01"
PS C:\> Add-AzureRouteConfig -Name "route13" -AddressPrefix 10.3.0.0/16 -NextHopType VnetLocal -RouteTable $RouteTable
```

The first command gets a route table named routetable01 by using the Get-AzureRouteTable cmdlet.
The command stores the table in the $RouteTable variable.

The second command adds a route named route13 to the route table stored in $RouteTable.
This route forwards packets to the local virtual network.

### Example 2: Add a route to a route table by using the pipeline
```
PS C:\>Get-AzureRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01" | Add-AzureRouteConfig -Name "route02" -AddressPrefix 10.2.0.0/16 -NextHopType VnetLocal | Set-AzureRouteTable
Name              : routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/routetable01
Etag              : W/"f13e1bc8-d41f-44d0-882d-b8b5a1134f59"
ProvisioningState : Succeeded
Tags              : 
Routes            : [
                      {
                        "Name": "route07",
                        "Etag": "W/\"f13e1bc8-d41f-44d0-882d-b8b5a1134f59\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route07",
                        "AddressPrefix": "10.1.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "route02",
                        "Etag": "W/\"f13e1bc8-d41f-44d0-882d-b8b5a1134f59\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route02",
                        "AddressPrefix": "10.2.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "route13",
                        "Etag": null, 
                        "Id": null, 
                        "AddressPrefix": "10.3.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": null
                      }
                    ] 
Subnets           : []
```

This command gets the route table named routetable01 by using **Get-AzureRouteTable**.
The command passes that table to the current cmdlet by using the pipeline operator.

The current cmdlet adds the route named route02, and then passes the result to the Set-AzureRouteTable cmdlet, which updates the table to reflect your changes.

## PARAMETERS

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

### -Name
Specifies a name of the route to add to the route table.

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
Specify this parameter only if you specify a value of VirtualAppliance for the *NextHopType* parameter.

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

- Internet.
The default Internet gateway provided by Azure. 
- None.
If you specify this value, the route does not forward packets. 
- VirtualAppliance.
A virtual appliance that you add to your Azure virtual network. 
- VirtualNetworkGateway.
An Azure server-to-server virtual private network gateway. 
- VnetLocal.
The local virtual network.
If you have two subnets, 10.1.0.0/16 and 10.2.0.0/16 in the same virtual network, select a value of VnetLocal for each subnet to forward to the other subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Internet, None, VirtualAppliance, VirtualNetworkGateway, VnetLocal

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteTable
Specifies the route table to which this cmdlet adds a route.

```yaml
Type: PSRouteTable
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

[Get-AzureRouteConfig](.\Get-AzureRouteConfig.md)

[Get-AzureRouteTable](.\Get-AzureRouteTable.md)

[New-AzureRouteConfig](.\New-AzureRouteConfig.md)

[Remove-AzureRouteConfig](.\Remove-AzureRouteConfig.md)

[Set-AzureRouteConfig](.\Set-AzureRouteConfig.md)

[Set-AzureRouteTable](.\Set-AzureRouteTable.md)

