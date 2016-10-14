---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayFrontendIPConfig.md
schema: 2.0.0
---

# Remove-AzureApplicationGatewayFrontendIPConfig

## SYNOPSIS
Removes a front-end IP configuration from an application gateway.

## SYNTAX

```
Remove-AzureApplicationGatewayFrontendIPConfig -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureApplicationGatewayFrontendIPConfig** cmdlet removes frontend IP from an Azure application gateway.

## EXAMPLES

### Example 1: Remove a front-end IP configuration
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIP02"
```

The first command gets an application gateway named ApplicationGateway01 and stores it in the $AppGw variable.

The second command removes the front-end IP configuration named FrontEndIP02 from the application gateway stored in $AppGw.

## PARAMETERS

### -ApplicationGateway
Specifies an application gateway from which to remove a front-end IP configuration.

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
Specifies the name of a front-end IP configuration to remove.

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

[Add-AzureApplicationGatewayFrontendIPConfig](.\Add-AzureApplicationGatewayFrontendIPConfig.md)

[Get-AzureApplicationGatewayFrontendIPConfig](.\Get-AzureApplicationGatewayFrontendIPConfig.md)

[New-AzureApplicationGatewayFrontendIPConfig](.\New-AzureApplicationGatewayFrontendIPConfig.md)

[Set-AzureApplicationGatewayFrontendIPConfig](.\Set-AzureApplicationGatewayFrontendIPConfig.md)

