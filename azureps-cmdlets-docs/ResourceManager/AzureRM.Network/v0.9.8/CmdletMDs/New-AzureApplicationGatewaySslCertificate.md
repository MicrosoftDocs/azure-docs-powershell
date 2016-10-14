---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewaySslCertificate.md
schema: 2.0.0
---

# New-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Creates an SSL certificate for an Azure application gateway.

## SYNTAX

```
New-AzureApplicationGatewaySslCertificate -Name <String> -CertificateFile <String> -Password <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewaySslCertificate** cmdlet creates an SSL certificate for an Azure application gateway.

## EXAMPLES

### Example 1: Create an SSL certificate for an azure_2 application gateway.
```
PS C:\>$Cert = New-AzureApplicationGatewaySslCertificate -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password "Password01"
```

This command creates a SSL certificate named Cert01 for the default application gateway.

## PARAMETERS

### -CertificateFile
Specifies the path of the .pfx file of the SSL certificate that this cmdlet creates.

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
Specifies the name of the SSL certificate that this cmdlet creates.

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
Specifies the password of the SSL that this cmdlet creates.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewaySslCertificate](.\Add-AzureApplicationGatewaySslCertificate.md)

[Get-AzureApplicationGatewaySslCertificate](.\Get-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](.\Remove-AzureApplicationGatewaySslCertificate.md)

[Set-AzureApplicationGatewaySslCertificate](.\Set-AzureApplicationGatewaySslCertificate.md)

