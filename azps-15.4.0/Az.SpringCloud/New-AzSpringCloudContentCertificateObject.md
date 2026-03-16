---
external help file: Az.SpringCloud-help.xml
Module Name: Az.SpringCloud
online version: https://learn.microsoft.com/powershell/module/Az.SpringCloud/new-azspringcloudcontentcertificateobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SpringCloud/SpringCloud/help/New-AzSpringCloudContentCertificateObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SpringCloud/SpringCloud/help/New-AzSpringCloudContentCertificateObject.md
cmdletStatusMessage: This cmdlet is part of a **Preview** module. Preview versions aren't recommended for use in production environments. For more information, see https://aka.ms/azps-refstatus.
cmdletStatus: preview
---
# New-AzSpringCloudContentCertificateObject

## SYNOPSIS
Create an in-memory object for ContentCertificateProperties.

## SYNTAX

```
New-AzSpringCloudContentCertificateObject [-Content <String>]
 [<CommonParameters>]
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

### Microsoft.Azure.PowerShell.Cmdlets.SpringCloud.Models.ContentCertificateProperties

## NOTES

## RELATED LINKS

