---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmApiManagementHostnameConfiguration

## SYNOPSIS
Creates an instance of **PsApiManagementHostnameConfiguration**.

## SYNTAX

```
New-AzureRmApiManagementHostnameConfiguration -CertificateThumbprint <String> -Hostname <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmApiManagementHostnameConfiguration** cmdlet is a helper command that creates an instance of **PsApiManagementHostnameConfiguration**.
This command is used with the **Set-AzureRmApiManagementHostnames** cmdlet.

## EXAMPLES

### Example 1: Create and initialize an instance of PsApiManagementHostnameConfiguration
```
PS C:\> New-AzureRmApiManagementHostnameConfiguration -Hostname "portal.contoso.com" -CertificateThumbprint "33CC47C6FCA848DC9B14A6F071C1EF7C"
```

This command creates and initializes an instance of **PsApiManagementHostnameConfiguration** for the custom hostname "portal.contoso.com".

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint.
Use the **Import-AzureRmApiManagementHostnameCertificate** cmdlet to import a certificate.

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

### -Hostname
Specifies the custom hostname for which this cmdlet creates the **PsApiManagementHostnameConfiguration** instance.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementHostnameConfiguration

## NOTES

## RELATED LINKS

[Import-AzureRmApiManagementHostnameCertificate](./Import-AzureRmApiManagementHostnameCertificate.md)

[Set-AzureRmApiManagementHostnames](./Set-AzureRmApiManagementHostnames.md)
