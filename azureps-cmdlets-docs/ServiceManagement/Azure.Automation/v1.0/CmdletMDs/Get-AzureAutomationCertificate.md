---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: .\New-AzureAutomationCertificate.md
schema: 2.0.0
---

# Get-AzureAutomationCertificate

## SYNOPSIS
Gets an Azure Automation certificate.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationCertificate [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByCertificateName
```
Get-AzureAutomationCertificate [-Name] <String> [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationCertificate** cmdlet gets one or more Microsoft Azure Automation certificates.
By default, all certificates are returned.
To get a specific certificate, specify its name.

## EXAMPLES

### Example 1: Get all certificates
```
PS C:\> Get-AzureAutomationCertificate -AutomationAccountName "Contoso17"
```

This command gets all certificates in the Azure Automation account named Contoso17.

### Example 2: Get a certificate
```
PS C:\> Get-AzureAutomationCertificate -AutomationAccountName "Contoso17" -Name "MyUserCertificate"
```

This command gets the certificate named MyUserCertificate.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the automation account with the certificate.

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

### -Name
Specifies the name of a certificate to retrieve.

```yaml
Type: String
Parameter Sets: ByCertificateName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

### Microsoft.Azure.Commands.Automation.Model.CertificateInfo

## NOTES

## RELATED LINKS

[New-AzureAutomationCertificate](.\New-AzureAutomationCertificate.md)

[Remove-AzureAutomationCertificate](.\Remove-AzureAutomationCertificate.md)

[Set-AzureAutomationCertificate](.\Set-AzureAutomationCertificate.md)

