---
external help file: RMAzure_Apimanagement.xml
online version: 2a7ef835-586c-4e86-a243-3cc0e9623d71
schema: 2.0.0
---

# New-AzureRmApiManagementHostnameConfiguration
## SYNOPSIS
Creates an instance of PsApiManagementHostnameConfiguration.

## SYNTAX

```
New-AzureRmApiManagementHostnameConfiguration -CertificateThumbprint <String> -Hostname <String>
```

## DESCRIPTION
The **New-AzureRmApiManagementHostnameConfiguration** cmdlet is a helper command that creates an instance of **PsApiManagementHostnameConfiguration**.
This command is used with the Set-AzureRmApiManagementHostnames cmdlet.

## EXAMPLES

### Example 1: Create and initialize an instance of PsApiManagementHostnameConfiguration
```
PS C:\>New-AzureRmApiManagementHostnameConfiguration -Hostname "portal.contoso.com" -CertificateThumbprint "33CC47C6FCA848DC9B14A6F071C1EF7C"
```

This command creates and initializes an instance of **PsApiManagementHostnameConfiguration**.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint.
The certificate must be first imported with the Import-AzureRmApiManagementHostnameCertificate cmdlet.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-AzureRmApiManagementHostnameCertificate](2a7ef835-586c-4e86-a243-3cc0e9623d71)

[Set-AzureRmApiManagementHostnames](dd997f04-b85b-409c-8c69-a5e659c768e3)

