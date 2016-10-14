---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewayHttpListener.md
schema: 2.0.0
---

# Add-AzureApplicationGatewayHttpListener

## SYNOPSIS
Adds an HTTP listener to an application gateway.

## SYNTAX

### SetByResourceId
```
Add-AzureApplicationGatewayHttpListener -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-FrontendIPConfigurationId <String>] [-FrontendPortId <String>] [-SslCertificateId <String>]
 -Protocol <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureApplicationGatewayHttpListener -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-FrontendIPConfiguration <PSApplicationGatewayFrontendIPConfiguration>]
 [-FrontendPort <PSApplicationGatewayFrontendPort>] [-SslCertificate <PSApplicationGatewaySslCertificate>]
 -Protocol <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApplicationGatewayHttpListener** cmdlet adds a HTTP listener to an application gateway.

## EXAMPLES

### Example 1: Add a HTTP listener
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Appgw = Add-AzureApplicationGatewayHttpListener -ApplicationGateway $AppGw -Name "listener01" -Protocol "Http" -FrontendIpConfiguration $FIP01 -FrontendPort $FP01
```

The first command gets the application gateway and stores it in the $AppGw variable.

The second command adds the HTTP listener to the application gateway.

### Example 2: Add a HTTPS listener with SSL
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureApplicationGatewayHttpListener -ApplicationGateway $AppGw
-Name "Listener01" -Protocol "Https" -FrontendIpConfiguration $FIP01 -FrontendPort $FP01 - SslCertificate $SSLCert01
```

The first command gets the application gateway and stores it in the $AppGw variable.

The second command adds the listener, which uses the HTTPS protocol, to the application gateway.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway to which this cmdlet adds an HTTP listener.

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

### -FrontendIPConfiguration
Specifies the application gateway front-end IP resource object.

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
Specifies the application gateway front-end IP ID.

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
Specifies the application gateway front-end port object.

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
Specifies the application gateway front-end port ID.

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
Specifies the name of the front-end port that this command adds.

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
Specifies the protocol of the HTTP listener.
Both HTTP and HTTPS are supported.

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
Specifies the SSL certificate of the HTTP listener.
Must be specified if HTTPS is chosen as listener protocol.

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
Specifies the SSL certificate ID of the HTTP listener.
Must be specified if HTTPS is chosen as listener protocol.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Get-AzureApplicationGatewayHttpListener](.\Get-AzureApplicationGatewayHttpListener.md)

[New-AzureApplicationGatewayHttpListener](.\New-AzureApplicationGatewayHttpListener.md)

[Remove-AzureApplicationGatewayHttpListener](.\Remove-AzureApplicationGatewayHttpListener.md)

[Set-AzureApplicationGatewayHttpListener](.\Set-AzureApplicationGatewayHttpListener.md)

