---
external help file: RMAzure_Automation.xml
online version: 048bf33a-0bc1-4433-92e0-bd906f6edb8d
schema: 2.0.0
---

# Set-AzureRMAutomationWebhook
## SYNOPSIS
Modifies a webhook for an Automation runbook.

## SYNTAX

```
Set-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-IsEnabled] <Boolean]> [[-Parameters] <IDictionary>]
```

## DESCRIPTION
The **Set-AzureRmAutomationWebhook** cmdlet modifies a webhook for an azure_2 Automation runbook.

## EXAMPLES

### Example 1: Disable a webhook
```
PS C:\>Set-AzureAutomationWebhook -Name "Webhook01" -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -IsEnabled $False
```

This command disables a webhook named Webhook01 in the Automation account named AutomationAccount01.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet modifies a webhook.

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

### -IsEnabled
Specifies whether the webhook is enabled.

```yaml
Type: Boolean]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name of the webhook that this cmdlet modifies.

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

### -Parameters
Specifies a dictionary of key/value pairs.
The keys are the runbook parameter names.
The values are the runbook parameter values.
When the runbook starts in response to a webhook, these parameters are passed to the runbook.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet modifies a webhook.

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

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationWebhook](048bf33a-0bc1-4433-92e0-bd906f6edb8d)

[New-AzureRmAutomationWebhook](cca289e3-4c75-48af-9f25-f99b0c6965c4)

[Remove-AzureRmAutomationWebhook](8dadbd54-8df1-4b9e-b853-97893e3ad73a)

