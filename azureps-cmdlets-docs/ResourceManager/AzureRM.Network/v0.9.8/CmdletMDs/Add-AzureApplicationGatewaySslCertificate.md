---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewaySslCertificate.md
schema: 2.0.0
---

# Add-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Adds an SSL certificate to an application gateway.

## SYNTAX

```
Add-AzureApplicationGatewaySslCertificate -ApplicationGateway <PSApplicationGateway> -Name <String>
 -CertificateFile <String> -Password <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApplicationGatewaySslCertificate** cmdlet adds an SSL certificate to an application gateway.

## EXAMPLES

### Example 1: Add an SSL certificate to an application gateway.
```
PS C:\>$AppGW = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGW = Add-AzureApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password "Password01"
```

This command gets an application gateway named ApplicationGateway01 and then adds an SSL certificate named Cert01 to it.

## PARAMETERS

### -ApplicationGateway
Specifies the name of application gateway to which this cmdlet adds an SSL certificate.```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateFile
Specifies the .pfx file of an SSL certificate that this cmdlet adds.

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

### -Name
Specifies the name of the SSL certificate that this cmdlet adds.

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

### -Password
Specifies the password of the SSL certificate that this cmdlet adds.

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

[Get-AzureApplicationGatewaySslCertificate](.\Get-AzureApplicationGatewaySslCertificate.md)

[New-AzureApplicationGatewaySslCertificate](.\New-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](.\Remove-AzureApplicationGatewaySslCertificate.md)

[Set-AzureApplicationGatewaySslCertificate](.\Set-AzureApplicationGatewaySslCertificate.md)

