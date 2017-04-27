---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApiManagementCertificate

## SYNOPSIS
Gets all or specific certificates.

## SYNTAX

### Get all certificates (Default)
```
Get-AzureRmApiManagementCertificate -Context <PsApiManagementContext>
```

### Get certificate by ID
```
Get-AzureRmApiManagementCertificate -Context <PsApiManagementContext> -CertificateId <String>
```

## DESCRIPTION
Gets all or specific certificates.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}

```
Get-AzureRmApiManagementCertificate -Context $apimContext
```

Get all certificates.

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}

```
Get-AzureRmApiManagementCertificate -Context $apimContext -CertificateId 0123456789
```

Get specific certificate.

## PARAMETERS

### -Context
Instance of PsApiManagementContext.
This parameter is required.

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

### -CertificateId
Identifier of the certificate.
If specified will find certificate by the identifier.
This parameter is required.

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

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementCertificate

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, api, apimanagement, apimgmt, apism

## RELATED LINKS

