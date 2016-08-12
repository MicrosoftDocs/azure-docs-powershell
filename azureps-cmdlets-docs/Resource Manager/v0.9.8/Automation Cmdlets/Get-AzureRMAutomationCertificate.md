---
external help file: RMAzure_Automation.xml
online version: 4316d596-2954-42e8-905f-840853dab7d5
schema: 2.0.0
---

# Get-AzureRMAutomationCertificate
## SYNOPSIS
Gets Automation certificates.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationCertificate** cmdlet gets one or more azure_2 Automation certificates.
By default, this cmdlet gets all certificates.
Specify the name of a certificate to get a specific certificate.

## EXAMPLES

### Example 1: Get all certificates
```
PS C:\>Get-AzureRmAutomationCertificate -ResourceGroupName "ResourceGroup07" -AutomationAccountName "Contoso17"
```

This command gets metadata for all certificates in the Automation account named Contoso17.

### Example 2: Get a certificate
```
PS C:\>Get-AzureRmAutomationCertificate -ResourceGroupName "ResourceGroup07" -AutomationAccountName "Contoso17" -Name "ContosoCertificate"
```

This command gets metadata for the certificate named ContosoCertificate.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet retrieves a certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a certificate to retrieve.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet gets an Automation certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CertificateInfo

## NOTES

## RELATED LINKS

[New-AzureRmAutomationCertificate](4316d596-2954-42e8-905f-840853dab7d5)

[Remove-AzureRmAutomationCertificate](1ed3a0d7-541d-4a07-b0d6-4538f98450f7)

[Set-AzureRmAutomationCertificate](77502783-0006-4288-917f-26f265ccfcbe)

