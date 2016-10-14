---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendAddressPool.md
schema: 2.0.0
---

# Remove-AzureApplicationGatewayBackendAddressPool

## SYNOPSIS
Removes a back-end address pool from an application gateway.

## SYNTAX

```
Remove-AzureApplicationGatewayBackendAddressPool -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureApplicationGatewayBackendAddressPool** cmdlet removes a back-end address pool from an Azure application gateway.

## EXAMPLES

### Example 1: Remove a back-end address pool from an application gateway
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw -Name "BackEndPool02"
```

The first command gets the application gateway named ApplicationGateway01 belonging to the resource group named ResourceGroup01 and saves it in the $AppGw variable.
The second command removes the back-end address pool named BackEndPool02 from the application gateway.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway from which this cmdlet removes a back-end address pool.

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
Specifies the name of the back-end address pool that this cmdlet removes.

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

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendAddressPool](.\Add-AzureApplicationGatewayBackendAddressPool.md)

[Get-AzureApplicationGatewayBackendAddressPool](.\Get-AzureApplicationGatewayBackendAddressPool.md)

[New-AzureApplicationGatewayBackendAddressPool](.\New-AzureApplicationGatewayBackendAddressPool.md)

[Set-AzureApplicationGatewayBackendAddressPool](.\Set-AzureApplicationGatewayBackendAddressPool.md)

