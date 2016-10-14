---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendAddressPool.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayBackendAddressPool

## SYNOPSIS
Gets a back-end address pool for an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewayBackendAddressPool [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### Example 1: Get a specified back-end server pool
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $BackendPool = Get-AzureApplicationGatewayBackendAddressPool -Name "Pool01" -ApplicationGateway $AppGw
```

The first command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01 and stores it in the $AppGw variable.

The second command gets the back-end address pool associated with $AppGw named Pool01 and stores it in the $BackendPool variable.

### Example 2: Get a list of back-end server pool
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $BackendPools = Get-AzureApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw
```

The first command gets the application gateway named ApplicationGateway01 in the resource group named ResourceGroup01 and stores it in the $AppGw variable.

The second command gets a list of the the back-end address pools associated with $AppGw, and stores the list in the $BackendPools variable.

## PARAMETERS

### -ApplicationGateway
The **Get-AzureApplicationGatewayBackendAddressPool** cmdlet gets a back-end address pool for an application gateway.

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
Specifies the name of the back-end address pool that this cmdlet gets.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendAddressPool](.\Add-AzureApplicationGatewayBackendAddressPool.md)

[New-AzureApplicationGatewayBackendAddressPool](.\New-AzureApplicationGatewayBackendAddressPool.md)

[Remove-AzureApplicationGatewayBackendAddressPool](.\Remove-AzureApplicationGatewayBackendAddressPool.md)

[Set-AzureApplicationGatewayBackendAddressPool](.\Set-AzureApplicationGatewayBackendAddressPool.md)

