---
external help file: RMAzure_Automation.xml
online version: a6dc9902-ad99-47f9-8212-d3d96146b180
schema: 2.0.0
---

# Remove-AzureRMAutomationVariable
## SYNOPSIS
Removes an Automation variable.

## SYNTAX

```
Remove-AzureRMAutomationVariable [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationVariable** cmdlet removes a variable from azure_2 Automation.

## EXAMPLES

### Example 1: Remove a variable
```
PS C:\>Remove-AzureRmAutomationVariable -AutomationAccountName "Contoso17" -Name "StringVariable22" -Force -ResourceGroupName "ResourceGroup01"
```

This command removes a variable named StringVariable22 in the Automation account named Contoso17.
This command specifies the *Force* parameter.
Therefore, it does not prompt you for confirmation.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the variable that this cmdlet deletes.

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
Specifies the name of the variable that this cmdlet deletes.

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
Specifies the resource group for which this cmdlet deletes a variable.

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

[Get-AzureRmAutomationVariable](a6dc9902-ad99-47f9-8212-d3d96146b180)

[New-AzureRmAutomationVariable](4103a716-9567-4836-b522-d2484452a60e)

[Set-AzureRmAutomationVariable](3bc5445e-7884-4dab-b00d-3bdfed9f05c5)

