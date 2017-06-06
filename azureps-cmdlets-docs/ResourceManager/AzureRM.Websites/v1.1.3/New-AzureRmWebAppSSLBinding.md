---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmWebAppSSLBinding

## SYNOPSIS
Creates a secure socket layer (SSL) certificate binding for a web app.

## SYNTAX

### S2
```
New-AzureRmWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-Name] <String> [[-SslState] <SslState>] [-Thumbprint] <String> [<CommonParameters>]
```

### S1
```
New-AzureRmWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-Name] <String> [[-SslState] <SslState>] [-CertificateFilePath] <String> [-CertificatePassword] <String>
 [<CommonParameters>]
```

### S3
```
New-AzureRmWebAppSSLBinding [-WebApp] <Site> [-Name] <String> [[-SslState] <SslState>]
 [-CertificateFilePath] <String> [-CertificatePassword] <String> [<CommonParameters>]
```

### S4
```
New-AzureRmWebAppSSLBinding [-WebApp] <Site> [-Name] <String> [[-SslState] <SslState>] [-Thumbprint] <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmWebAppSSLBinding** cmdlet creates a secure socket layer (SSL) certificate binding for a web app that was built using the Web Apps feature of the Azure App Service.
The cmdlet creates an SSL binding in either of the following two ways:

- By binding a Web App to an existing certificate.
- By uploading a new certificate and then binding the web app to this new certificate.

Regardless of which approach you use, the certificate and the web app must be associated with the same Azure resource group.
If you have a web app in resource group A and you want to bind that web app to a certificate in resource group B, you must upload a copy of the certificate to resource group A.

If you upload a new certificate, keep in mind the following requirements for an Azure SSL certificate:

- The certificate must contain a private key.
- The certificate must use the Personal Information Exchange (PFX) file format.
- The certificate's subject name must match the domain used to access the web app.
- The certificate must use a minimum of 2048-bit encryption.

## EXAMPLES

### Example 1: Bind a certificate to a web app
```
PS C:\> New-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" -Name "www.contoso.com" -CertificatePassword "p@ssw0rd"
```

This command binds an existing Azure certificate with the thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" to the web app named "ContosoWebApp".

### Example 2: Upload a certificate and bind it to a Web App
```
PS C:\> New-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" -Name "www.contoso.com" -CertificatePassword "p@ssw0rd" -CertificateFilePath "C:\Certificates\ContosoWebSite.pfx"
```

This command also binds an existing Azure certificate with the thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" to the web app named "ContosoWebApp".
However, in this case, the certificate has not yet been uploaded to Azure.
The local copy of the certificate, specified by the *CertificateFilePath* parameter, will be uploaded to Azure and then the new SSL bindings will be created.

## PARAMETERS

### -CertificateFilePath
Specifies the file path of the local copy of the certificate to be uploaded. This parameter is required only if the certificate has not yet been uploaded to Azure.

```yaml
Type: String
Parameter Sets: S1, S3
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePassword
Specifies the decryption password for the certificate.

```yaml
Type: String
Parameter Sets: S1, S3
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the SSL binding.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group to which the certificate is assigned.
You cannot use the *ResourceGroupName* parameter and the *WebApp* parameter in the same command.

```yaml
Type: String
Parameter Sets: S2, S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Specifies the name of the slot to which the web app is deployed.

Deployment slots provide a way for you to stage and validate web apps without those apps being accessible over the Internet.
Typically you will deploy your changes to a staging site, validate those changes, and then deploy to the production (Internet-accessible) site.

```yaml
Type: String
Parameter Sets: S2, S1
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslState
Specifies whether the certificate is enabled.
Set this parameter to 1 to enable the certificate; set this parameter to 0 to disable the certificate.

```yaml
Type: SslState
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the unique identifier for of the certificate.

```yaml
Type: String
Parameter Sets: S2, S4
Aliases:

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Specifies a **WebApp** object that contains details about the web app.

```yaml
Type: Site
Parameter Sets: S3, S4
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebAppName
Specifies the name of the web app for which this cmdlet creates an SSL binding.
You cannot use the *WebAppName* parameter and the *WebApp* parameter in the same command.

```yaml
Type: String
Parameter Sets: S2, S1
Aliases:

Required: True
Position: 1
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

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)

[Get-AzureRMWebAppSlot](./Get-AzureRMWebAppSlot.md)

[Get-AzureRmWebAppSSLBinding](./Get-AzureRmWebAppSSLBinding.md)

[Remove-AzureRmWebAppSSLBinding](./Remove-AzureRmWebAppSSLBinding.md)
