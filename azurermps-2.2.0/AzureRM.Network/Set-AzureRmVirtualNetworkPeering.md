---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmVirtualNetworkPeering

## SYNOPSIS
Sets a virtual network peering

## SYNTAX

```
Set-AzureRmVirtualNetworkPeering -VirtualNetworkPeering <PSVirtualNetworkPeering>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
This cmdlet sets virtual network peering.
It is especially helpful when updates to configurations of a peering are made as it ensures the changes or updates made successfully.

## EXAMPLES

### --------------------------  Example 1 Changing forward traffic configuration of a Virtual Network Peering  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $LinkToVNet2 = Get-AzureRmVirtualNetworkPeering -VirtualNetworkName "MyVirtualNetwork" ResourceGroupName "MyResourceGroup" -Name LinkToVNet2
PS C:\> $LinkToVNet2.AllowForwardedTraffic = $true
PS C:\> Set-AzureRmVirtualNetworkPeering -VirtualNetworkPeering $LinkToVNet2
```

This example shows how to change the forwarded traffic configuration to true instead of the default false option on a previously established VNet peering link.
The first command gets the associated information regarding the link, in this case, called LinkToVNet2 within "MyResourceGroup" in virtual network "MyVirtualNetwork".
The next command updates the variable property to true.
The final command changes the setting for the "LinkToVNet2" virtual network peering link to true.

### --------------------------  Example 2 Changing Virtual Network Access of a Virtual Network Peering  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $LinkToVNet2 = Get-AzureRmVirtualNetworkPeering -VirtualNetworkName "MyVirtualNetwork" ResourceGroupName "MyResourceGroup" -Name LinkToVNet2
PS C:\> $LinkToVNet2.AllowVirtualNetworkAccess = $false
PS C:\> Set-AzureRmVirtualNetworkPeering -VirtualNetworkPeering $LinkToVNet2
```

This example shows how to change the Virtual Network Access property configuration to false instead of the default true option on a previously established VNet peering link.
The first command gets the associated information regarding the link, in this case, called LinkToVNet2 within "MyResourceGroup" in virtual network "MyVirtualNetwork".
The next command updates the variable associated with the property to false.
The final command changes the setting for the "LinkToVNet2" virtual network peering link to false.

### --------------------------  Example 3 Changing Gateway Transit property configuration of a Virtual Network Peering  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $LinkToVNet2 = Get-AzureRmVirtualNetworkPeering -VirtualNetworkName "MyVirtualNetwork" ResourceGroupName "MyResourceGroup" -Name LinkToVNet2
PS C:\> $LinkToVNet2.AllowGatewayTransit = $true
PS C:\> Set-AzureRmVirtualNetworkPeering -VirtualNetworkPeering $LinkToVNet2
```

This example shows how to change the gateway transit property configuration to true instead of the default false option on a previously established VNet peering link.
The first command gets the associated information regarding the link, in this case, called LinkToVNet2 within "MyResourceGroup" in virtual network "MyVirtualNetwork".
The next command updates the variable associated with this property to true.
The final command changes the setting for the "LinkToVNet2" virtual network peering link to true.
By changing this property to true, the peer VNet is allowed to use your VNet gateway.

### --------------------------  Example 4 Making use of remote gateways in Virtual Network Peering  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $LinkToVNet2 = Get-AzureRmVirtualNetworkPeering -VirtualNetworkName "MyVirtualNetwork" ResourceGroupName "MyResourceGroup" -Name LinkToVNet2

PS C:\> $LinkToVNet2.UseRemoteGateways = $true

PS C:\> Set-AzureRmVirtualNetworkPeering -VirtualNetworkPeering $LinkToVNet2
```

This example shows how to change the remote gateway configuration to true instead of the default false option on a previously established VNet peering link.
The first command gets the associated information regarding the link, in this case, called LinkToVNet2 within "MyResourceGroup" in virtual network "MyVirtualNetwork".
The next command changes the configuration to true.
The final command changes the setting for the "LinkToVNet2" virtual network peering link to true.
By changing this property to true, your peer's VNet gateway can be used.
However, the peer VNet must have a gateway configured and AllowGatewayTransit must be configured to true.
This property cannot be utilized if a gateway has already been configured previously.

## PARAMETERS

### -VirtualNetworkPeering
The virtual network peering

```yaml
Type: PSVirtualNetworkPeering
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

## RELATED LINKS

[Get-AzureRmVirtualNetworkPeering]()

[Remove-AzureRmVirtualNetworkPeering]()

[Add-AzureRmVirtualNetworkPeering]()

