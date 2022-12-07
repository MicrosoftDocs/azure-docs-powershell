---
external help file: 
Module Name: Az.SpringCloud
online version: https://docs.microsoft.com/powershell/module/az.SpringCloud/new-AzSpringCloudContentCertificateObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SpringCloud/help/New-AzSpringCloudContentCertificateObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SpringCloud/help/New-AzSpringCloudContentCertificateObject.md
---

# New-AzSpringCloudContentCertificateObject

## SYNOPSIS
Create an in-memory object for ContentCertificateProperties.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.springcloud/new-azspringcloudcontentcertificateobject) for up-to-date information.

## SYNTAX

```
New-AzSpringCloudContentCertificateObject [-Content <String>] [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for ContentCertificateProperties.

## EXAMPLES

### Example 1: Create an in-memory object for ContentCertificateProperties
```powershell
New-AzSpringCloudContentCertificateObject -Content "ContentCertificate"
```

```output
ActivateDate DnsName ExpirationDate IssuedDate Issuer SubjectName Thumbprint Content
------------ ------- -------------- ---------- ------ ----------- ---------- -------
                                                                             ContentCertificate
```

Create an in-memory object for ContentCertificateProperties.

## PARAMETERS

### -Content
The content of uploaded certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.SpringCloud.Models.Api20220401.ContentCertificateProperties

## NOTES

ALIASES

## RELATED LINKS

