---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmRouteConfig

## SYNOPSIS
Removes a route from a route table.

## SYNTAX

```
Remove-AzureRmRouteConfig -Name <String> -RouteTable <PSRouteTable> [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureRmRouteConfig cmdlet removes a route from an Azure route table.

## EXAMPLES

### --------------------------  Example 1: Remove a route  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01" | Remove-AzureRmRouteConfig -Name "route02" | Set-AzureRmRouteTable
Name              : routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/routetable01
Etag              : W/"47099b62-60ec-4bc1-b87b-fad56cb8bed1"
ProvisioningState : Succeeded
Tags              :
Routes            : [
                      {
                        "Name": "route07",
                        "Etag": "W/\"47099b62-60ec-4bc1-b87b-fad56cb8bed1\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route07",
                        "AddressPrefix": "10.1.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null,
                        "ProvisioningState": "Succeeded"
                      }
                    ]
Subnets           : []
```

This command gets the route table named routetable01 by using the Get-AzureRmRouteTable cmdlet.
The command passes that table to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -Name
Specifies the name of the route that this cmdlet removes.

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

### -RouteTable
Specifies the route table that contains the route that this cmdlet deletes.

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
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmRouteConfig]()

[Get-AzureRmRouteConfig]()

[New-AzureRmRouteConfig]()

[Set-AzureRmRouteConfig]()

