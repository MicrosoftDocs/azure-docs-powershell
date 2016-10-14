---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewaySslCertificate.md
schema: 2.0.0
---

# Get-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Gets an SSL certificate for an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewaySslCertificate [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewaySslCertificate** cmdlet gets an SSL certificate for an application gateway.

## EXAMPLES

### Example 1: Get a specific SSL certificate
```
PS C:\>$AppGW = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Cert = Get-AzureApplicationGatewaySslCertificate -Name "Cert01" -ApplicationGateway $AppGW
```

This command gets the SSL certificate named Cert01 from the application gateway named ApplicationGateway01.

### Example 2: Get a list of SSL certificates
```
PS C:\>$AppGW = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Certs = Get-AzureApplicationGatewaySslCertificate -ApplicationGateway $AppGW
```

This command gets a list of SSL certificates from the application gateway named ApplicationGateway01.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway object that contains the SSL certificate.```yaml
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
Specifies the name of SSL certificate pool that this cmdlet gets.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewaySslCertificate](.\Add-AzureApplicationGatewaySslCertificate.md)

[New-AzureApplicationGatewaySslCertificate](.\New-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](.\Remove-AzureApplicationGatewaySslCertificate.md)

[Set-AzureApplicationGatewaySslCertificate](.\Set-AzureApplicationGatewaySslCertificate.md)

