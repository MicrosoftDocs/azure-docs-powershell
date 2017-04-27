---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmVirtualNetworkPeering

## SYNOPSIS
Gets a Virtual Network Peering to view the status of VNet peering link

## SYNTAX

```
Get-AzureRmVirtualNetworkPeering -VirtualNetworkName <String> -ResourceGroupName <String> [-Name <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
This cmdlet gets the virtual network peering specified by the user in the cmdlet.
Note that there must be an existing peering in order to get it via this cmdlet.
This cmdlet is a good way to check if a peering was successfully created.

Look into Add-AzureRmVirtualNetworkPeering to create this peering if you have not created a peering already.

## EXAMPLES

### --------------------------  Example 1 Get a peering between 2 virtual networks  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmVirtualNetworkPeering -Name "LinkToVNet2" -VirtualNetwork "MyVirtualNetwork" -ResourceGroupName "MyResourceGroup"
```

This command gets a previously created Virtual Network Peering called "LinkToVNet2" located in "MyVirtualNetwork" within the resource group called "MyResourceGroup"

## PARAMETERS

### -VirtualNetworkName
The virtual network name

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

### -ResourceGroupName
The resource group name.

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
The virtual network peering name.

```yaml
Type: String
Parameter Sets: (All)
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

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking, peering

## RELATED LINKS

[Remove-AzureRmVirtualNetworkPeering]()

[Add-AzureRmVirtualNetworkPeering]()

[Set-AzureRmVirtualNetworkPeering]()

