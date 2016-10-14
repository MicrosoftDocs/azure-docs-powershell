---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureServiceDiagnosticsExtension.md
schema: 2.0.0
---

# New-AzureServiceDiagnosticsExtensionConfig

## SYNOPSIS
Generates a configuration for a diagnostics extension for specified role(s) or all roles.

## SYNTAX

### NewExtension (Default)
```
New-AzureServiceDiagnosticsExtensionConfig [[-Role] <String[]>] [[-X509Certificate] <X509Certificate2>]
 [[-ThumbprintAlgorithm] <String>] [-StorageContext] <AzureStorageContext>
 [[-DiagnosticsConfigurationPath] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### NewExtensionUsingThumbprint
```
New-AzureServiceDiagnosticsExtensionConfig [[-Role] <String[]>] [-CertificateThumbprint] <String>
 [[-ThumbprintAlgorithm] <String>] [-StorageContext] <AzureStorageContext>
 [[-DiagnosticsConfigurationPath] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureServiceDiagnosticsExtensionConfig** cmdlet generates a configuration for a diagnostics extension for specified roles or all roles.

## EXAMPLES

### Example 1: Generate a configuration for a diagnostics extension
```
PS C:\>$wadConfig = New-AzureServiceDiagnosticExtensionConfig -StorageAccountName $Name -DiagnosticConfiguration $WadConfigXML
```

This command generates a configuration for a diagnostics extension.

### Example 2: Generate a configuration for a diagnostics extension for a specified role
```
PS C:\>$wadConfig = New-AzureServiceDiagnosticExtensionConfig -StorageAccountName $Name -DiagnosticConfiguration $WadConfigXML -Role "WebRole01"
```

This command generates a configuration for a diagnostics extension for the role named WebRole01.

## PARAMETERS

### -Role
Specifies an optional array of roles to specify the diagnostics configuration for.
If not specified the diagnostics configuration is applied as the default configuration for all roles.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -X509Certificate
Specifies an X.509 certificate that is automatically uploaded to the cloud service and used for encrypting the extension private configuration.

```yaml
Type: X509Certificate2
Parameter Sets: NewExtension
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThumbprintAlgorithm
Specifies a thumbprint hashing algorithm which is used with the thumbprint to identify the certificate.
This parameter is optional and the default is sha1.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext
Specifies an Azure storage context.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiagnosticsConfigurationPath
Specifies the diagnostics configuration path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies a certificate thumbprint to use to encrypt the private configuration.
This certificate has to already exist in the certificate store.
If you do not specify a certificate, this cmdlet creates a certificate.

```yaml
Type: String
Parameter Sets: NewExtensionUsingThumbprint
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-AzureServiceDiagnosticsExtension](.\Get-AzureServiceDiagnosticsExtension.md)

[Set-AzureServiceDiagnosticsExtension](.\Set-AzureServiceDiagnosticsExtension.md)

