---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmVirtualNetworkSubnetConfig

## SYNOPSIS
Removes a subnet configuration from a virtual network.

## SYNTAX

```
Remove-AzureRmVirtualNetworkSubnetConfig [-Name <String>] -VirtualNetwork <PSVirtualNetwork>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Remove-AzureRmVirtualNetworkSubnetConfig cmdlet removes a subnet from an Azure virtual network.
This cmdlet only removes the subnet config from an in-memory representation of the virtual network.
To update a virtual network, a cmdlet such as Set-AzureRmVirtualNetwork can be called.

## EXAMPLES

### --------------------------  Example 1: Remove a subnet from a virtual network and update the virtual network  --------------------------
@{paragraph=PS C:\\\>}

```
New-AzureRmResourceGroup -Name TestResourceGroup -Location centralus
$frontendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name frontendSubnet -AddressPrefix "10.0.1.0/24"
$backendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name backendSubnet -AddressPrefix "10.0.2.0/24"
$virtualNetwork = New-AzureRmVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName TestResourceGroup -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $frontendSubnet,$backendSubnet
Remove-AzureRmVirtualNetworkSubnetConfig -Name backendSubnet -VirtualNetwork $virtualNetwork
$virtualNetwork | Set-AzureRmVirtualNetwork
```

This example creates a resource group and a virtual network with two subnets.
It then uses the Remove-AzureRmVirtualNetworkSubnetConfig command to remove the backend subnet from the in-memory representation of the virtual network.
Set-AzureRmVirtualNetwork is then called to modify the virtual network on the server side.

## PARAMETERS

### -Name
Specifies the name of the subnet configuration to remove.

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

### -VirtualNetwork
Specifies the VirtualNetwork object that contains the subnet configuration to remove.

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
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmVirtualNetworkSubnetConfig]()

[Get-AzureRmVirtualNetworkSubnetConfig]()

[New-AzureRmVirtualNetworkSubnetConfig]()

[Set-AzureRmVirtualNetworkSubnetConfig]()

