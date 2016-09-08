---
external help file: RMAzure_Automation.xml
online version: 68762a05-73e2-4987-aac6-1021282cdad7
schema: 2.0.0
---

# Remove-AzureRmAutomationModule
## SYNOPSIS
Removes a module from Automation.

## SYNTAX

```
Remove-AzureRmAutomationModule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationModule** cmdlet removes a module from an Automation account in azure_2 Automation.

## EXAMPLES

### Example 1: Remove a module
```
PS C:\>Remove-AzureRmAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ResourceGroupName "ResourceGroup01"
```

This command removes a module named ContosoModule from the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account from which this cmdlet removes a module.

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

### -Force
ps_force

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the module that this cmdlet removes.

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
Specifies the name of a resource group in which this cmdlet removes a module.

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

[Get-AzureRmAutomationModule](68762a05-73e2-4987-aac6-1021282cdad7)

[New-AzureRmAutomationModule](0cfa1dd4-11f2-4eb6-a354-46bf4286d00f)

[Set-AzureRmAutomationModule](e47306c4-b17e-4651-8248-eb81ad448a17)

