---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnCustomDomainTlsSettingParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject.md
---

# New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject

## SYNOPSIS
Create an in-memory object for AFDDomainHttpsParameters.

## SYNTAX

```
New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject -CertificateType <AfdCertificateType>
 [-MinimumTlsVersion <AfdMinimumTlsVersion>] [-Secret <IResourceReference>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for AFDDomainHttpsParameters.

## EXAMPLES

### Example 1: Create an in-memory object for AFDDomainHttpsParameters
```powershell
$secret =  Get-AzFrontDoorCdnSecret -ResourceGroupName testps-rg-da16jm -ProfileName fdp-v542q6 -Name secret001
$secretResource = New-AzFrontDoorCdnResourceReferenceObject -Id $secret.Id
New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject -CertificateType "CustomerCertificate" -MinimumTlsVersion "TLS12" -Secret $secretResource
```

```output
CertificateType     MinimumTlsVersion
---------------     -----------------
CustomerCertificate TLS12
```

Create an in-memory object for AFDDomainHttpsParameters

## PARAMETERS

### -CertificateType
Defines the source of the SSL certificate.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdCertificateType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTlsVersion
TLS protocol version that will be used for Https.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdMinimumTlsVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Secret
Resource reference to the secret.
ie.
subs/rg/profile/secret.
To construct, see NOTES section for SECRET properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20240201.IResourceReference
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20240201.AfdDomainHttpsParameters

## NOTES

## RELATED LINKS
