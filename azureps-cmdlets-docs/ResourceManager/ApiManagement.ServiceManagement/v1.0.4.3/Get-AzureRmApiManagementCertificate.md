---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementCertificate

## SYNOPSIS
Gets all Azure API Management certificates or a specific certificate.

## SYNTAX

### Get all certificates (Default)
```
Get-AzureRmApiManagementCertificate -Context <PsApiManagementContext> [<CommonParameters>]
```

### Get certificate by ID
```
Get-AzureRmApiManagementCertificate -Context <PsApiManagementContext> -CertificateId <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementCertificate** cmdlet gets all Azure API Management certificates or a specific certificate.

## EXAMPLES

### Example 1: Get all certificates
```
PS C:\> Get-AzureRmApiManagementCertificate -Context $ApiMgmtContext
```

This command gets all API Management certificates.

### Example 2: Get a specific certificate by its ID
```
PS C:\> Get-AzureRmApiManagementCertificate -Context $ApiMgmtContext -CertificateId "0123456789"
```

This command gets the API Management certificate identified by the ID "0123456789".

## PARAMETERS

### -CertificateId
Specifies the ID of the certificate to get.

```yaml
Type: String
Parameter Sets: Get certificate by ID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Context
Specifies an **PsApiManagementContext** object that contains details about the context of the Azure API Management service.

```yaml
Type: PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

## OUTPUTS

### System.Collections.Generic.IList
### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementCertificate

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementCertificate](./New-AzureRmApiManagementCertificate.md)

[Remove-AzureRmApiManagementCertificate](./Remove-AzureRmApiManagementCertificate.md)

[Set-AzureRmApiManagementCertificate](./Set-AzureRmApiManagementCertificate.md)
