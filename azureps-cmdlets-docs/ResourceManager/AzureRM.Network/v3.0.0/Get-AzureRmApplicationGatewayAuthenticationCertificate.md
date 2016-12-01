---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E50724AF-1433-4C46-ABDD-91CE827DF70E
---

# Get-AzureRmApplicationGatewayAuthenticationCertificate

## SYNOPSIS
Gets an authentication certificate for an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewayAuthenticationCertificate [-Name <String>]
 -ApplicationGateway <PSApplicationGateway> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApplicationGatewayAuthenticationCertificate** cmdlet gets an authentication certificate for an Azure application gateway.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the authentication certificate that this cmdlet gets.

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

### -ApplicationGateway
Specifies the name of application gateway for which this cmdlet gets an authentication certificate.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAuthenticationCertificate

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayAuthenticationCertificate](./Add-AzureRmApplicationGatewayAuthenticationCertificate.md)

[New-AzureRmApplicationGatewayAuthenticationCertificate](./New-AzureRmApplicationGatewayAuthenticationCertificate.md)

[Remove-AzureRmApplicationGatewayAuthenticationCertificate](./Remove-AzureRmApplicationGatewayAuthenticationCertificate.md)

[Set-AzureRmApplicationGatewayAuthenticationCertificate](./Set-AzureRmApplicationGatewayAuthenticationCertificate.md)


