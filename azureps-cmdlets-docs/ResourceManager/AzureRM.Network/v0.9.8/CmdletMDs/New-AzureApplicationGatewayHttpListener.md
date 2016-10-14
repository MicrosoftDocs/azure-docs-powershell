---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayHttpListener.md
schema: 2.0.0
---

# New-AzureApplicationGatewayHttpListener

## SYNOPSIS
Creates an HTTP listener for an application gateway.

## SYNTAX

### SetByResourceId
```
New-AzureApplicationGatewayHttpListener -Name <String> [-FrontendIPConfigurationId <String>]
 [-FrontendPortId <String>] [-SslCertificateId <String>] -Protocol <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByResource
```
New-AzureApplicationGatewayHttpListener -Name <String>
 [-FrontendIPConfiguration <PSApplicationGatewayFrontendIPConfiguration>]
 [-FrontendPort <PSApplicationGatewayFrontendPort>] [-SslCertificate <PSApplicationGatewaySslCertificate>]
 -Protocol <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewayHttpListener** cmdlet creates an HTTP listener for an Azure application gateway.

## EXAMPLES

### Example 1: Create an HTTP listener
```
PS C:\>$Listener = New-AzureApplicationGatewayHttpListener -Name "Listener01" -Protocol "Http" -FrontendIpConfiguration $FIp01 -FrontendPort $FP01
```

This command creates an HTTP listener.

### Example 2: Create an HTTP listener with SSL
```
PS C:\>$Listener = New-AzureApplicationGatewayHttpListener -Name "Listener01" -Protocol "Https" -FrontendIpConfiguration $FIp01 -FrontendPort $FP01 - SslCertificate $SSLCert01
```

This command creates an HTTP listener that uses SSL offload and provides the SSL certificate in the $SSLCert01 variable.

## PARAMETERS

### -FrontendIPConfiguration
Specifies front-end IP configuration object for the HTTP listener.

```yaml
Type: PSApplicationGatewayFrontendIPConfiguration
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIPConfigurationId
Specifies the ID of the front-end IP configuration for the HTTP listener.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendPort
Specifies the front-end port for the HTTP listener.

```yaml
Type: PSApplicationGatewayFrontendPort
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendPortId
Specifies the ID of the front-end port object for the HTTP listener.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the HTTP listener that this cmdlet creates.

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

### -Protocol
Specifies the protocol that the HTTP listener uses.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Http, Https

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslCertificate
Specifies the SSL certificate object for  the HTTP listener.

```yaml
Type: PSApplicationGatewaySslCertificate
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslCertificateId
Specifies the ID of the SSL certificate for the HTTP listener.

```yaml
Type: String
Parameter Sets: SetByResourceId
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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSHttpListener

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayHttpListener](.\Add-AzureApplicationGatewayHttpListener.md)

[Get-AzureApplicationGatewayHttpListener](.\Get-AzureApplicationGatewayHttpListener.md)

[Remove-AzureApplicationGatewayHttpListener](.\Remove-AzureApplicationGatewayHttpListener.md)

[Set-AzureApplicationGatewayHttpListener](.\Set-AzureApplicationGatewayHttpListener.md)

