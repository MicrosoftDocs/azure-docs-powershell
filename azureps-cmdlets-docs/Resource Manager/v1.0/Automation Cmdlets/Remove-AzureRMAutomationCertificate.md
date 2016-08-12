---
external help file: RMAzure_Automation.xml
online version: 7e2d3105-ae14-40c6-a715-57d63c178cde
schema: 2.0.0
---

# Remove-AzureRMAutomationCertificate
## SYNOPSIS
Removes an Automation certificate.

## SYNTAX

```
Remove-AzureRMAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationCertificate** cmdlet removes a certificate from azure_2 Automation.

## EXAMPLES

### Example 1: Remove a certificate
```
PS C:\>Remove-AzureRmAutomationCertificate -AutomationAccountName "Contoso17" -Name "Cert01" -ResourceGroupName "ResourceGroup01"
```

This command removes a certificate named Cert01 in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet removes a certificate.

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
Specifies the name of the certificate that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet removes a certificate.

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

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationCertificate](7e2d3105-ae14-40c6-a715-57d63c178cde)

[New-AzureRmAutomationCertificate](4316d596-2954-42e8-905f-840853dab7d5)

[Set-AzureRmAutomationCertificate](77502783-0006-4288-917f-26f265ccfcbe)

