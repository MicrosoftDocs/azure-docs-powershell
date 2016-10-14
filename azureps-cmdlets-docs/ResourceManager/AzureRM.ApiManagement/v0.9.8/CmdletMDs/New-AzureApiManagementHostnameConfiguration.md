---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version: .\Import-AzureApiManagementHostnameCertificate.md
schema: 2.0.0
---

# New-AzureApiManagementHostnameConfiguration

## SYNOPSIS
Creates an instance of PsApiManagementHostnameConfiguration.

## SYNTAX

```
New-AzureApiManagementHostnameConfiguration -CertificateThumbprint <String> -Hostname <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApiManagementHostnameConfiguration** cmdlet is a helper command that creates an instance of **PsApiManagementHostnameConfiguration**.
This command is used with the Set-AzureApiManagementHostnames cmdlet.

## EXAMPLES

### Example 1
```
PS C:\>New-AzureApiManagementHostnameConfiguration -Hostname "portal.contoso.com" -CertificateThumbprint "33CC47C6FCA848DC9B14A6F071C1EF7C"
```

Create and initialize instance of Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementHostnameConfiguration type.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint.
The certificate must be first imported with the Import-AzureApiManagementHostnameCertificate cmdlet.

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
Specifies the custom host name for which this cmdlet creates the **PsApiManagementHostnameConfiguration** instance.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-AzureApiManagementHostnameCertificate](.\Import-AzureApiManagementHostnameCertificate.md)

[Set-AzureApiManagementHostnames](.\Set-AzureApiManagementHostnames.md)

