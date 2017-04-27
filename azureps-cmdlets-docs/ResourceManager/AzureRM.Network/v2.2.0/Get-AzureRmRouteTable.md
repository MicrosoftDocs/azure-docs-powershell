---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmRouteTable

## SYNOPSIS
Gets route tables.

## SYNTAX

### Expand
```
Get-AzureRmRouteTable -Name <String> -ResourceGroupName <String> -ExpandResource <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### NoExpand
```
Get-AzureRmRouteTable [-Name <String>] [-ResourceGroupName <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmRouteTable cmdlet gets Azure route tables.
You can retrieve a single route table, or retrieve all the route tables in a resource group or in your subscription.

## EXAMPLES

### --------------------------  Example 1: Get a route table  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>Get-AzureRmRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01"
Name              : routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/routetable01
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

This command gets the route table named routetable01 in the resource group named ResourceGroup11.

## PARAMETERS

### -Name
Specifies the name of the route table that this cmdlet gets.

```yaml
Type: String
Parameter Sets: Expand
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: NoExpand
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the route tables that this cmdlet gets.

```yaml
Type: String
Parameter Sets: Expand
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: NoExpand
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
@{Text=}

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
@{Text=}

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

### -ExpandResource
@{Text=}

```yaml
Type: String
Parameter Sets: Expand
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[New-AzureRmRouteTable]()

[Remove-AzureRmRouteTable]()

[Set-AzureRmRouteTable]()

