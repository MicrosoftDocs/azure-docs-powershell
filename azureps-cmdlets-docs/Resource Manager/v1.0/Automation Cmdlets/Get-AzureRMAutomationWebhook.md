---
external help file: RMAzure_Automation.xml
online version: cca289e3-4c75-48af-9f25-f99b0c6965c4
schema: 2.0.0
---

# Get-AzureRMAutomationWebhook
## SYNOPSIS
Gets webhooks from Automation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String> -Name <String>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -RunbookName <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationWebhook** cmdlet gets webhooks.
To get specific webhooks, specify a webhook name or specify the name of an azure_2 Automation runbook to get the webhooks connected to it.

## EXAMPLES

### Example 1: Get all webhooks for a runbook
```
PS C:\>Get-AzureRmAutomationWebhook -RunbookName "Runbook03" -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01"
```

This command gets all webhooks for a runbook named Runbook03 in the Automation account named AutomationAccount01 in the resource group named ResourceGroup01.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet gets a webhook.

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
Specifies the name of the webhook that this cmdlet gets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: WebhookName

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet gets webhooks.

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

### -RunbookName
Specifies the name of a runbook for which this cmdlet gets webhooks.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmAutomationWebhook](cca289e3-4c75-48af-9f25-f99b0c6965c4)

[Remove-AzureRmAutomationWebhook](8dadbd54-8df1-4b9e-b853-97893e3ad73a)

[Set-AzureRmAutomationWebhook](b2f5cd9e-5886-4ccc-89ea-9e66e5c67818)

