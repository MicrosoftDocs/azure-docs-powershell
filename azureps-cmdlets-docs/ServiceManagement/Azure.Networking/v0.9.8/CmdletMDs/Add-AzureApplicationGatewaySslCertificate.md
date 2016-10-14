---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewaySslCertificate.md
schema: 2.0.0
---

# Add-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Adds an SSL certificate to an application gateway.

## SYNTAX

```
Add-AzureApplicationGatewaySslCertificate [-Name] <String> [-CertificateName] <String> [-Password] <String>
 [-CertificateFile] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApplicationGatewaySslCertificate** cmdlet adds a Secure Sockets Layer (SSL) certificate to an application gateway.

## EXAMPLES

### Example 1: Add an SSL certificate
```
PS C:\>Add-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08" -CertificateName "SslCertificate13" -Password "password" -CertificateFile "c:\Certs\sslCertificate.pfx"
```

This command adds an SSL certificate named SslCertificate13 to the application gateway named ApplicationGateway08.
The command specifies the path of the certificate file and the password for the certificate.

## PARAMETERS

### -Name
Specifies the name of the application gateway to which this cmdlet adds an SSL certificate.

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
This cmdlet adds the certificate that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies the password of the SSL certificate that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateFile
Specifies the path of an SSL certificate file.
This cmdlet adds the certificate in the file that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureApplicationGatewaySslCertificate](.\Get-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](.\Remove-AzureApplicationGatewaySslCertificate.md)

