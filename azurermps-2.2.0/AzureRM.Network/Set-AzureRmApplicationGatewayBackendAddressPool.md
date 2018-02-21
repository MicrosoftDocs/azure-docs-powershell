---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmApplicationGatewayBackendAddressPool

## SYNOPSIS
Updates a back-end address pool for an application gateway.

## SYNTAX

### SetByResourceId
```
Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendIPConfigurationIds <System.Collections.Generic.List`1[System.String]>] [<CommonParameters>]
```

### SetByIP
```
Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendIPAddresses <System.Collections.Generic.List`1[System.String]>] [<CommonParameters>]
```

### SetByFqdn
```
Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendFqdns <System.Collections.Generic.List`1[System.String]>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmApplicationGatewayBackendAddressPool cmdlet updates a back-end address pool for an Azure application gateway.
Back-end addresses can be specified as IP addresses, fully-qualified domain names (FQDN) or IP configurations IDs.

## EXAMPLES

### Example 1: Setting a backend address pool by using FQDNs

```
PS C:\>$AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw
-Name "Pool02" -BackendFqdns "contoso1.com", "contoso2.com"
```

The first command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01, and stores it in the $AppGw variable.

### Example 2: Setting a backend address pool by using backend server IP addresses

```
PS C:\>$AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw
-Name "Pool02" -BackendIPAddresses "10.10.10.10", "10.10.10.11"
```

The second command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01, and stores it in the $AppGw variable.

### Example 3: Setting a backend address pool by using the ID of the backend server's IP address

```
PS C:\>$Nic01 = Get-AzureRmNetworkInterface -Name "Nic01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Nic02 = Get-AzureRmNetworkInterface -Name "Nic02" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw
-Name "Pool02" -BackendIPConfigurationIds $nic01.Properties.IpConfigurations[0].Id, $nic02.Properties.IpConfiguration[0].Id
```

The first command gets a network interface object named Nic01 that belongs to the resource group named ResourceGroup01, and stores it in the $Nic01 variable.

The forth command uses the back-end IP configuration IDs from $Nic01 and $Nic02 to update the back-end address pool of the application gateway in $AppGw.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway with which this cmdlet associates the back-end address pool.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the back-end address pool.
This back-end address pool must exist in the application gateway.

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

### -BackendIPConfigurationIds
Specifies a list of back-end IP configuration IDs to use for the back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendIPAddresses
Specifies a list of back-end IP addresses to use as a back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByIP
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendFqdns
Specifies a list of back-end FQDNs to use as a back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByFqdn
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayBackendAddressPool]()

[Get-AzureRmApplicationGatewayBackendAddressPool]()

[Get-AzureRmNetworkInterface]()

[New-AzureRmApplicationGatewayBackendAddressPool]()

[Remove-AzureRmApplicationGatewayBackendAddressPool]()
