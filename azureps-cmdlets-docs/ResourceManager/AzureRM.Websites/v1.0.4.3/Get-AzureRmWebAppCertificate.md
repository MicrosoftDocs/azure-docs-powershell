---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmWebAppCertificate

## SYNOPSIS
Gets web app certificates.

## SYNTAX

```
Get-AzureRmWebAppCertificate [[-ResourceGroupName] <String>] [[-Thumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmWebAppCertificate** cmdlet gets web app certificates that are associated with a resource group.
If you know the certificate thumbprint, you can also use this cmdlet to get information about a specific certificate.

## EXAMPLES

### Example 1: Get a specific web app certificate
```
PS C:\> Get-AzureRmWebAppCertificate -ResourceGroupName "Contoso" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

This command gets the certificate with the thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" associated with the "Contoso" resource group.

## PARAMETERS

### -ResourceGroupName
Specifies the resource group with which the certificate is associated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureRmWebAppSSLBinding](./Get-AzureRmWebAppSSLBinding.md)
