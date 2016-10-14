---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayFrontendIPConfig.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayFrontendIPConfig

## SYNOPSIS
Gets the front-end IP configuration of an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewayFrontendIPConfig [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewayFrontendIPConfig** cmdlet gets the front-end IP configuration of an application gateway.

## EXAMPLES

### Example 1: Get a specified front-end IP configuration
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndIP= Get-AzureApplicationGatewayFrontendIPConfig -Name "FrontEndIP01" -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command gets the front-end IP configuration named FrontEndIP01 from $AppGw and stores it in the $FrontEndIP variable.

### Example 2: Get a list of front-end IP configurations
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndIPs= Get-AzureApplicationGatewayFrontendIPConfig  -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command gets a list of the front-end IP configurations from $AppGw and stores it in the $FrontEndIPs variable.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway object that contains the front-end IP configuration.

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
Specifies the name of the front-end IP configuration that this cmdlet gets.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayFrontendIPConfig](.\Add-AzureApplicationGatewayFrontendIPConfig.md)

[New-AzureApplicationGatewayFrontendIPConfig](.\New-AzureApplicationGatewayFrontendIPConfig.md)

[Remove-AzureApplicationGatewayFrontendIPConfig](.\Remove-AzureApplicationGatewayFrontendIPConfig.md)

[Set-AzureApplicationGatewayFrontendIPConfig](.\Set-AzureApplicationGatewayFrontendIPConfig.md)

