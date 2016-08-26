---
external help file: RMAzure_Automation.xml
online version: 048bf33a-0bc1-4433-92e0-bd906f6edb8d
schema: 2.0.0
---

# New-AzureRMAutomationWebhook
## SYNOPSIS
Creates a webhook for an Automation runbook.

## SYNTAX

```
New-AzureRMAutomationWebhook [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-RunbookName] <String> [-IsEnabled] <Boolean> [-ExpiryTime] <DateTimeOffset> [-Force]
 [-Parameters <IDictionary>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-AzureRmAutomationWebhook** cmdlet creates a webhook for an azure_2 Automation runbook.

Be sure to save the webhook URL that this cmdlet returns, because it cannot be retrieved again.

## EXAMPLES

### Example 1: Create a webhook
```
PS C:\>$Webhook = New-AzureRmAutomationWebhook -Name "Webhook06" -IsEnabled $True -ExpiryTime "10/2/2016" -RunbookName "ContosoRunbook" -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -Force
```

This command creates a webhook named Webhook06 for the runbook named ContosoRunbook in the Automation account named AutomationAccount01.
The command stores the webhook in the $Webhook variable.
The webhook is enabled.
The webhook expires at the specified time.
This command does not provide any values for webhook parameters.
This command specifies the *Force* parameter.
Therefore, it does not prompt you for confirmation.

### Example 2: Create a webhook with parameters
```
PS C:\>$Params = @{"StringParam"="Hello World";"IntegerParam"=32}
PS C:\> $Webhook = New-AzureRmAutomationWebhook -Name "Webhook11" -Parameters $Params -IsEnabled $True -ExpiryTime "10/2/2016" -RunbookName "ContosoRunbook" -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -Force
```

The first command creates a dictionary of parameters, and stores them in the $Params variable.

The second command creates a webhook named Webhook11 for the runbook named ContosoRunbook in the Automation account named AutomationAccount01.
The command assigns the parameters in $Params to the webhook.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet creates a webhook.

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

### -ExpiryTime
Specifies the expiry time for the webhook as a **DateTimeOffset** object.
You can specify a string or a **DateTime** that can be converted to a valid **DateTimeOffset**.

```yaml
Type: DateTimeOffset
Parameter Sets: (All)
Aliases: 

Required: True
Position: 6
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsEnabled
Specifies whether the webhook is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the webhook.

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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet creates a webhook.

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
Specifies the name of the runbook to associate to the webhook.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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

[Remove-AzureRmAutomationWebhook](8dadbd54-8df1-4b9e-b853-97893e3ad73a)

[Set-AzureRmAutomationWebhook](b2f5cd9e-5886-4ccc-89ea-9e66e5c67818)

