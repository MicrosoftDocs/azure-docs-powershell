---
external help file: RMAzure_Automation.xml
online version: ea09d4b6-ff25-4b91-b957-328222844689
schema: 2.0.0
---

# Remove-AzureRMAutomationCredential
## SYNOPSIS
Removes an Automation credential.

## SYNTAX

```
Remove-AzureRMAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationCredential** cmdlet removes a credential from azure_2 Automation.

## EXAMPLES

### Example 1: Remove a credential
```
PS C:\>Remove-AzureRmAutomationCredential -AutomationAccountName "Contoso17" -Name "ContosoCredential" -ResourceGroupName "ResourceGroup01"
```

This command removes a credential named ContosoCredential in the azure_2 Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account from which this cmdlet removes a credential.

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
Specifies the name of the credential that this cmdlet removes.

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
Specifies the name of the resource group for which this cmdlet removes a credential.

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

[Get-AzureRmAutomationCredential](ea09d4b6-ff25-4b91-b957-328222844689)

[New-AzureRmAutomationCredential](2e0b5b0e-df2b-4747-bb42-8e6b94f397e0)

[Set-AzureRmAutomationCredential](f0f039fd-2b0b-4993-8408-471e0f7ad10b)

