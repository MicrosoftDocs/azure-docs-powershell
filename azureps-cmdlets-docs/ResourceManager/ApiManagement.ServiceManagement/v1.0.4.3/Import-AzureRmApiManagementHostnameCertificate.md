---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Import-AzureRmApiManagementHostnameCertificate

## SYNOPSIS
Imports a certificate in PFX format for an API Management service.

## SYNTAX

```
Import-AzureRmApiManagementHostnameCertificate -ResourceGroupName <String> -Name <String>
 -HostnameType <PsApiManagementHostnameType> -PfxPath <String> -PfxPassword <String> [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureRmApiManagementHostnameCertificate** cmdlet imports a certificate in PFX format for an API Management service.
The certificate is used for configuration of custom hostnames.

## EXAMPLES

### Example 1: Import a proxy hostname certificate
```
PS C:\> Import-AzureRmApiManagementHostnameCertificate -Name "ContosoApi" -ResourceGroupName "Contoso" -HostnameType "Proxy" -PfxPath "C:\proxycert.pfx" -PfxPassword "CertSecret"
```

This command imports a proxy hostname certificate for the API Management deployment named "ContosoApi".

## PARAMETERS

### -HostnameType
Specifies the hostname type for the certificate.

```yaml
Type: PsApiManagementHostnameType
Parameter Sets: (All)
Aliases:
Accepted values: Proxy, Portal

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the API Management deployment for which the certificate is being imported.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies whether to send a **PsApiManagementHostnameCertificate** object to the pipeline if this operation succeeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PfxPassword
Specifies the password for the .pfx certificate file from which to import the certificate.

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

### -PfxPath
Specifies the path of a .pfx certificate file from which to import the certificate.

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

### -ResourceGroupName
Specifies the name of the of resource group under which the API Management deployment exists.

```yaml
Type: String
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

### System.String
### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementHostnameType

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementHostnameCertificate

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementHostnameConfiguration](./New-AzureRmApiManagementHostnameConfiguration.md)

[Set-AzureRmApiManagementHostnames](./Set-AzureRmApiManagementHostnames.md)
