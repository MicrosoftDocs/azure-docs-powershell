---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewaySslCertificate.md
schema: 2.0.0
---

# Get-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Gets Application Gateway certificates.

## SYNTAX

```
Get-AzureApplicationGatewaySslCertificate [-Name] <String> [[-CertificateName] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewaySslCertificate** cmdlet gets Secure Sockets Layer (SSL) certificates for an Azure Application Gateway.

## EXAMPLES

### Example 1: Get an SSL certificate
```
PS C:\>Get-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08" -CertificateName "SslCertificate13"
```

This command gets an SSL certificate named SslCertificate13 on the Application Gateway named ApplicationGateway08.

### Example 2: Get all SSL certificates
```
PS C:\>Get-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08"
```

This command gets all the SSL certificates on the Application Gateway named ApplicationGateway08.

## PARAMETERS

### -Name
Specifies the name of the Application Gateway from which this cmdlet gets an SSL certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateName
Specifies the name of an SSL certificate.
This cmdlet gets the certificate that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
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

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayCertificate, List<Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayCertificate>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewaySslCertificate](.\Add-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](.\Remove-AzureApplicationGatewaySslCertificate.md)

