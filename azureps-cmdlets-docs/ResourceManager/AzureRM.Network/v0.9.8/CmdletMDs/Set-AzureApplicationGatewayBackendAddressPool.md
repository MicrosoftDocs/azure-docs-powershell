---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendAddressPool.md
schema: 2.0.0
---

# Set-AzureApplicationGatewayBackendAddressPool

## SYNOPSIS
Updates a back-end address pool for an application gateway.

## SYNTAX

### SetByResourceId
```
Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendIPConfigurationIds <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByIP
```
Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendIPAddresses <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByFqdn
```
Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendFqdns <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureApplicationGatewayBackendAddressPool** cmdlet updates a back-end address pool for an Azure application gateway.
Back-end addresses can be specified as IP addresses, fully-qualified domain names (FQDN) or IP configurations IDs.

## EXAMPLES

### Example 1: Setting a back-end address pool by using FQDNs
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw 
-Name "Pool02" -BackendFqdns "contoso1.com", "contoso2.com"
```

The first command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command updates the back-end address pool of the application gateway in $AppGw by using FQDNs.

### Example 2: Setting a back-end address pool by using backend server IP addresses
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw 
-Name "Pool02" -BackendIPAddresses "10.10.10.10", "10.10.10.11"
```

The second command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command updates the back-end address pool of the application gateway in $AppGw by using IP addresses.

### Example 3: Setting a back-end address pool by using the ID of the backend server's IP address
```
PS C:\>$Nic01 = Get-AzureNetworkInterface -Name "Nic01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Nic02 = Get-AzureNetworkInterface -Name "Nic02" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureApplicationGatewayBackendAddressPool -ApplicationGateway $ AppGw 
-Name "Pool02" -BackendIPConfigurationIds $nic01.Properties.IpConfigurations[0].Id, $nic02.Properties.IpConfiguration[0].Id
```

The first command gets a network interface object named Nic01 that belongs to the resource group named ResourceGroup01, and stores it in the $Nic01 variable.

The second command gets a network interface object named Nic02 that belongs to the resource group named ResourceGroup02, and stores it in the $Nic02 variable.

The third command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01, and stores it in the $AppGw variable.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendAddressPool](.\Add-AzureApplicationGatewayBackendAddressPool.md)

[Get-AzureApplicationGatewayBackendAddressPool](.\Get-AzureApplicationGatewayBackendAddressPool.md)

[Get-AzureNetworkInterface](.\Get-AzureNetworkInterface.md)

[New-AzureApplicationGatewayBackendAddressPool](.\New-AzureApplicationGatewayBackendAddressPool.md)

[Remove-AzureApplicationGatewayBackendAddressPool](.\Remove-AzureApplicationGatewayBackendAddressPool.md)

