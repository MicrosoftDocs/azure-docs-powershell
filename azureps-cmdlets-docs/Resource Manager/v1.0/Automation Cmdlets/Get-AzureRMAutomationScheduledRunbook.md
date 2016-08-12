---
external help file: RMAzure_Automation.xml
online version: 34edfa3b-7ef9-4aab-bb17-5ea725a22ed4
schema: 2.0.0
---

# Get-AzureRMAutomationScheduledRunbook
## SYNOPSIS
Gets Automation runbooks and associated schedules.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -JobScheduleId <Guid]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -RunbookName <String> -ScheduleName <String>
```

### UNNAMED_PARAMETER_SET_4
```
Get-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -RunbookName <String>
```

### UNNAMED_PARAMETER_SET_5
```
Get-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -ScheduleName <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationScheduledRunbook** cmdlet gets one or more azure_2 Automation runbooks and associated schedules.
By default, this cmdlet gets all scheduled runbooks.
Specify the name of a runbook or a schedule or both to see specific runbook schedules.

## EXAMPLES

### Example 1: Get all scheduled runbooks
```
PS C:\>Get-AzureRmAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

This command gets all scheduled runbooks in the azure_2 Automation account named Contoso17.

### Example 2: Get all schedules associated with a runbook
```
PS C:\>Get-AzureRmAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbk01"
```

This command gets all scheduled runbooks for the runbook Runbk01 in the azure_2 Automation account named Contoso17.

### Example 3: Get all runbooks associated with a schedule
```
PS C:\>Get-AzureRmAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -ScheduleName "Schedule01"
```

This command gets all scheduled runbooks for the schedule Schedule01 in the azure_2 Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies an Automation account for the runbook on which this cmdlet operates.

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

### -JobScheduleId
Specifies the ID of a scheduled job that this cmdlet gets.

```yaml
Type: Guid]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for scheduled runbooks that this cmdlet gets.

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
Specifies the name of a runbook for which this cmdlet gets scheduled runbooks.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleName
Specifies the name of a schedule for which this cmdlet gets scheduled runbooks.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.JobSchedule

## NOTES

## RELATED LINKS

[Register-AzureRmAutomationScheduledRunbook](34edfa3b-7ef9-4aab-bb17-5ea725a22ed4)

[Unregister-AzureRmAutomationScheduledRunbook](a56fc467-f64d-4453-9b55-cdd5cad1aa98)

