---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureCertificate.md
schema: 2.0.0
---

# Remove-AzureCertificate

## SYNOPSIS
Removes a certificate from an Azure service.

## SYNTAX

```
Remove-AzureCertificate [-ServiceName] <String> [-ThumbprintAlgorithm] <String> [-Thumbprint] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureCertificate** cmdlet removes a certificate from an Azure service.

## EXAMPLES

### Example 1: Remove a certificate from a service
```
PS C:\>Remove-AzureCertificate -ServiceName "ContosoService" -Thumbprint '5383CE0343CB6563281CA97C1D4D712209CFFA97'
```

This command removes the certificate object that has the specified thumbprint from the cloud service.

### Example 2: Remove all certificates from a service
```
PS C:\>Get-AzureCertificate -ServiceName "ContosoService" | Remove-AzureCertificate
```

This command gets all the certificates from the service named ContosoService by using the Get-AzureCertificate cmdlet.
The command passes each certificate to the current cmdlet by using the pipeline operator.
That cmdlet removes each certificate from the cloud service.

### Example 3: Remove all certificates from a service that use a specific thumbprint algorithm
```
PS C:\>Get-AzureCertificate -ServiceName "ContosoService" -ThumbprintAlgorithm "sha1" | Remove-AzureCertificate
```

This command gets all the certificates from the service named ContosoService that use the sha1 thumbprint algorithm.
The command passes each certificate to the current cmdlet, which removes each certificate.

## PARAMETERS

### -ServiceName
Specifies the name of the Azure service from which this cmdlet removes a certificate.

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

### -ThumbprintAlgorithm
Specifies the algorithm that is used to create the certificate thumbprint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### ManagementOperationContext

## NOTES

## RELATED LINKS

[Add-AzureCertificate](.\Add-AzureCertificate.md)

[Get-AzureCertificate](.\Get-AzureCertificate.md)

[New-AzureCertificateSetting](.\New-AzureCertificateSetting.md)

