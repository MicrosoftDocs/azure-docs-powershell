---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
ms.assetid: 7688CE56-0A25-4409-9676-BF1B67C3F05F
online version: 
schema: 2.0.0
---

# Get-AzureRmVirtualNetworkSubnetConfig

## SYNOPSIS
Gets a subnet in a virtual network.

## SYNTAX

```
Get-AzureRmVirtualNetworkSubnetConfig [-Name <String>] -VirtualNetwork <PSVirtualNetwork>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmVirtualNetworkSubnetConfig** cmdlet gets one or more subnet configurations in an Azure virtual network.

## EXAMPLES

### Example 1: Get a subnet in a virtual network 
```
PS C:\> New-AzureRmResourceGroup -Name "ResourceGroup03" -Location centralus
PS C:\> $FrontendSubnet = New-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -AddressPrefix "10.0.1.0/24"
PS C:\> $VirtualNetwork = New-AzureRmVirtualNetwork -Name "MyVirtualNetwork" -ResourceGroupName "ResourceGroup03" -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $FrontendSubnet
PS C:\> Get-AzureRmVirtualNetworkSubnetConfig -Name "FrontendSubnet" -VirtualNetwork $VirtualNetwork
```

The first command creates a resource group named ResourceGroup03 by using the **New-AzureRmResourceGroup** cmdlet.

The second command creates a subnet called FrontendSubnet by using the **New-AzureRmVirtualNetworkSubnetConfig** cmdlet, and stores it in the $FrontendSubnet variable.

The third command creates a virtual network named MyVirtualNetwork, and stores it in the $VirtualNetwork variable.

The final command gets data about the subnet named FrontendSubnet in the new virtual network.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

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
Specifies an information variable.

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

### -Name
Specifies the name of the subnet configuration that this cmdlet gets.

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
Specifies the **VirtualNetwork** object that contains the subnet configuration that this cmdlet gets.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmVirtualNetworkSubnetConfig](./Add-AzureRmVirtualNetworkSubnetConfig.md)

[New-AzureRmResourceGroup](./New-AzureRmResourceGroup.md)
 
[New-AzureRmVirtualNetwork](./New-AzureRmVirtualNetwork.md)

[New-AzureRmVirtualNetworkSubnetConfig](./New-AzureRmVirtualNetworkSubnetConfig.md)

[Remove-AzureRmVirtualNetworkSubnetConfig](./Remove-AzureRmVirtualNetworkSubnetConfig.md)

[Set-AzureRmVirtualNetworkSubnetConfig](./Set-AzureRmVirtualNetworkSubnetConfig.md)
