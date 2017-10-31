---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRmVirtualNetworkPeering

## SYNOPSIS
Creates a peering between 2 virtual networks

## SYNTAX

```
Add-AzureRmVirtualNetworkPeering -Name <String> -VirtualNetwork <PSVirtualNetwork>
 -RemoteVirtualNetworkId <String> [-BlockVirtualNetworkAccess] [-AllowForwardedTraffic] [-AlloowGatewayTransit]
 [-UseRemoteGateways] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
This cmdlet creates a peering between two virtual networks in the same region.
When two networks are peered, they will appear as one for all connectivity purposes.
Even though they will be managed as separate resources, virtual machines in these virtual networks are able to communicate with each other directly using private IP addresses due to peering.

## EXAMPLES

### --------------------------  Example 1 Create a peering between 2 virtual networks  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $vnet1 = Get-AzureRmVirtualNetwork -ResourceGroupName "MyResourceGroup" -Name vnet1
PS C:\> $vnet2 = Get-AzureRmVirtualNetwork -ResourceGroupName "MyResourceGroup" -Name vnet2
PS C:\> Add-AzureRmVirtualNetworkPeering -Name LinkToVNet2 -VirtualNetwork "MyVirtualNetwork" -RemoteVirtualNetworkId $vnet2.id
PS C:\> Add-AzureRmVirtualNetworkPeering -Name LinkToVNet1 -VirtualNetwork "MyVirtualNetwork" -RemoteVirtualNetworkId $vnet1.id
```

The first command gets a virtual network object called vnet1 associated with resource group "MyResourceGroup".
Similarly, the second command gets a virtual network object called vnet2 associated with the same resource group.
The third command then adds a Vnet peering link from vnet1 to vnet2.
This link is named LinkToVnet2.
Finally, the forth command adds a link from vnet2 to vnet1 called LinkToVnet1.
Note that vnet1 and vnet2 are assumed to be previously created in this example.
Note that a link must be created from vnet1 to vnet2 and vice versa in order for peering to work.

Below is example output for this example:

Name                             : LinkToVNet2
Id                               : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/provi
                                   ders/Microsoft.Network/virtualNetworks/MyVirtualNetwork/virtualNetworkPeerings/LinkToVNet2
Etag                             : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
ResourceGroupName                : MyResourceGroup
VirtualNetworkName               : MyVirtualNetwork
PeeringState                     : Initiated
ProvisioningState                : Succeeded
RemoteVirtualNetwork             : {
                                     "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx/resourceGroups/MyResourceGroup
                                   /providers/Microsoft.Network/virtualNetworks/MyVirtualNetwork"
                                   }
AllowVirtualNetworkAccess        : True
AllowForwardedTraffic            : False
AllowGatewayTransit              : False
UseRemoteGateways                : False
RemoteGateways                   : null
RemoteVirtualNetworkAddressSpace : null



Name                             : LinkToVNet1
Id                               : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx/resourceGroups/MyResourceGroup/provi
                                   ders/Microsoft.Network/virtualNetworks/MyVirtualNetwork/virtualNetworkPeerings/LinkToVNet1
Etag                             : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx"
ResourceGroupName                : MyResourceGroup
VirtualNetworkName               : MyVirtualNetwork
PeeringState                     : Initiated
ProvisioningState                : Succeeded
RemoteVirtualNetwork             : {
                                     "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx/resourceGroups/MyResourceGroup
                                   /providers/Microsoft.Network/virtualNetworks/MyVirtualNetwork"
                                   }
AllowVirtualNetworkAccess        : True
AllowForwardedTraffic            : False
AllowGatewayTransit              : False
UseRemoteGateways                : False
RemoteGateways                   : null
RemoteVirtualNetworkAddressSpace : null

## PARAMETERS

### -Name
The name of the virtual network peering

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

### -VirtualNetwork
The parent virtualNetwork

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

### -RemoteVirtualNetworkId
Reference to the remote virtual network

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BlockVirtualNetworkAccess
Flag to block the VMs in the linked virtual network space to access all the VMs in local Virtual network space

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

### -AllowForwardedTraffic
Flag to allow the forwarded traffic from the VMs in the remote virtual network

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

### -AlloowGatewayTransit
Flag to allow gatewayLinks be used in remote virtual network's link to this virtual network

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: AllowGatewayTransit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseRemoteGateways
Flag to allow remote gateways be used on this virtual network

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

[Get-AzureRmVirtualNetworkPeering]()

[Remove-AzureRmVirtualNetworkPeering]()

[Set-AzureRmVirtualNetworkPeering]()

