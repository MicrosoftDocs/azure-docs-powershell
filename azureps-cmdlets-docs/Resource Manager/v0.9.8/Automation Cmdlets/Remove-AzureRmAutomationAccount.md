---
external help file: RMAzure_Automation.xml
online version: c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43
schema: 2.0.0
---

# Remove-AzureRmAutomationAccount
## SYNOPSIS
Removes an Automation account.

## SYNTAX

```
Remove-AzureRmAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationAccount** cmdlet removes an azure_2 Automation account from a resource group.

For more information about Automation accounts, see the New-AzureRmAutomationAccount cmdlet.

## EXAMPLES

### Example 1: Remove an automation account
```
PS C:\>Remove-AzureRmAutomationAccount -Name "ContosoAutomationAccount" -Force -ResourceGroupName "ResourceGroup01"
```

This command removes an automation account named ContosoAutomationAccount without prompting for user validation.

## PARAMETERS

### -Force
ps_force

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the Automation account that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group from which this cmdlet removes an Automation account.

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

[Get-AzureRmAutomationAccount](c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43)

[New-AzureRmAutomationAccount](1a996e7a-1de8-4533-a39a-c17cf1ab18fd)

[Set-AzureRmAutomationAccount](7e2254d6-c3c3-4ec5-8f7d-a3a2a6f24969)

