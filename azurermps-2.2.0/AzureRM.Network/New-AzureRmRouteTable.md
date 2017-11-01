---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmRouteTable

## SYNOPSIS
Creates a route table.

## SYNTAX

```
New-AzureRmRouteTable -Name <String> -ResourceGroupName <String> -Location <String>
 [-Route <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSRoute]>]
 [-Tag <Hashtable[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmRouteTable cmdlet creates an Azure route table.

## EXAMPLES

### --------------------------  Example 1: Create a route table that contains a route  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$Route = New-AzureRmRouteConfig -Name "route07" -AddressPrefix 10.1.0.0/16 -NextHopType VnetLocal
PS C:\> New-AzureRmRouteTable -Name "routetable01" -ResourceGroupName "ResourceGroup11" -Location EASTUS -Route $Route
Name              : routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/myroutetable
Etag              : W/"db5f4e12-3f34-465b-92dd-0ab3bf6fc274"
ProvisioningState : Succeeded
Tags              :
Routes            : [
                      {
                        "Name": "route07",
                        "Etag": "W/\"db5f4e12-3f34-465b-92dd-0ab3bf6fc274\"",
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

The first command creates a route named route07 by using the New-AzureRmRouteConfig cmdlet, and then stores it in the $Route variable.
This route forwards packets to the local virtual network.

## PARAMETERS

### -Name
Specifies a name for the route table.

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
Specifies the name of the resource group in which this cmdlet creates a route table.

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

### -Location
Specifies the Azure region in which this cmdlet creates a route table.
For more information, see Azure Regions (http://azure.microsoft.com/en-us/regions/).

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

### -Route
Specifies an array of Route objects to associate with the route table.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSRoute]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies a dictionary of tags to associate with the route table.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet creates a route table even if a route table that has the same name already exists.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmRouteTable]()

[New-AzureRmRouteConfig]()

[Remove-AzureRmRouteTable]()

[Set-AzureRmRouteTable]()

