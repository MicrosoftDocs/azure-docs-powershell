---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\New-AzureAutomationCertificate.md
schema: 2.0.0
---

# Get-AzureAutomationCertificate

## SYNOPSIS
Gets Automation certificates.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByCertificateName
```
Get-AzureAutomationCertificate [-Name] <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationCertificate** cmdlet gets one or more Azure Automation certificates.
By default, this cmdlet gets all certificates.
Specify the name of a certificate to get a specific certificate.

## EXAMPLES

### Example 1: Get all certificates
```
PS C:\>Get-AzureAutomationCertificate -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
```

This command gets metadata on all certificates in the Automation account named Contoso17.

### Example 2: Get a certificate
```
PS C:\>Get-AzureAutomationCertificate -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -Name "MyUserCertificate"
```

This command gets metadata on the certificate named MyUserCertificate.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet retrieves a certificate.

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

### -ResourceGroupName
The resource group name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

