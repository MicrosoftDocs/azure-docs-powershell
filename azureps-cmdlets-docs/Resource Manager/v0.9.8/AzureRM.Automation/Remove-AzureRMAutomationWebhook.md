---
external help file: RMAzure_Automation.xml
online version: 048bf33a-0bc1-4433-92e0-bd906f6edb8d
schema: 2.0.0
---

# Remove-AzureRMAutomationWebhook
## SYNOPSIS
Removes a webhook from an Automation runbook.

## SYNTAX

```
Remove-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationWebhook** cmdlet removes a webhook from an azure_2 Automation runbook.
The webhook is deleted.

## EXAMPLES

### Example 1: Remove a webhook
```
PS C:\>Remove-AzureRmAutomationWebhook -Name "Webhook11" -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -Force
```

This command removes a webhook named Webhook11 in the Automation account named AutomationAccount01.
The command specifies the *Force* parameter.
Therefore, it does not prompt you for confirmation.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account from which this cmdlet removes a webhook.

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
Specifies the name of the webhook that this cmdlet removes.

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
Specifies the name of the resource group for which this cmdlet removes a webhook.

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

[Get-AzureRmAutomationWebhook](048bf33a-0bc1-4433-92e0-bd906f6edb8d)

[New-AzureRmAutomationWebhook](cca289e3-4c75-48af-9f25-f99b0c6965c4)

[Set-AzureRmAutomationWebhook](b2f5cd9e-5886-4ccc-89ea-9e66e5c67818)

