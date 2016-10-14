---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureCertificate.md
schema: 2.0.0
---

# Add-AzureCertificate

## SYNOPSIS
Uploads a certificate to an azure_2 cloud service.

## SYNTAX

```
Add-AzureCertificate [-ServiceName] <String> [-CertToDeploy] <Object> [-Password <String>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureCertificate** cmdlet uploads a certificate for an azure_2 service.

## EXAMPLES

### Example 1: Upload a certificate and password
```
PS C:\>Add-AzureCertificate -ServiceName "ContosoService" -CertToDeploy ContosoCertificate.pfx -Password "password"
```

This command uploads the certificate file ContosoCertificate.pfx to a cloud service.
The command specifies the password for the certificate.

### Example 2: Upload a certificate file
```
PS C:\>Add-AzureCertificate -serviceName "MyService" -CertToDeploy ContosoCertificate.cer
```

This command uploads the certificate file ContosoCertificate.cer to a cloud service.
The command specifies the password for the certificate.

### Example 3: Upload a certificate object
```
PS C:\>$Certificate = Get-Item cert:\PATTIFULLER\MY\1D6E34B526723E06C235BE8E5457784BF12C9F39
PS C:\> Add-AzureCertificate -ServiceName "ContosoService" -CertToDeploy $Certificate
```

The first command gets a certificate from the MY store of a user by using the wps_2 core Get-Item cmdlet.
The command stores the certificate in the $Certificate variable.

The second command uploads the certificate in $certificate to a cloud service.

## PARAMETERS

### -ServiceName
Specifies the name of the azure_2 service to which this cmdlet adds a certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertToDeploy
Specifies the certificate to deploy.
You can specify the full path of a certificate file, such as a file that has a *.cer or *.
pfx file name extension, or an X.509 Certificate object.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the certificate password.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

### ManagementOperationContext

## NOTES

## RELATED LINKS

[Get-AzureCertificate](.\Get-AzureCertificate.md)

[New-AzureCertificateSetting](.\New-AzureCertificateSetting.md)

[Remove-AzureCertificate](.\Remove-AzureCertificate.md)

