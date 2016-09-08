---
external help file: RMAzure_Automation.xml
online version: cfac4e12-2a1f-4b2c-873b-f5a3f9c4a2ce
schema: 2.0.0
---

# Unregister-AzureRMAutomationScheduledRunbook
## SYNOPSIS
Removes an association between a runbook and a schedule.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Unregister-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Force] -JobScheduleId <Guid]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Unregister-AzureRMAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Force] -RunbookName <String> -ScheduleName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Unregister-AzureRmAutomationScheduledRunbook** cmdlet removes the association between an azure_2 Automation runbook and a schedule.
The schedule no longer starts the runbook.

## EXAMPLES

### Example 1: Remove the association between a runbook and a schedule
```
PS C:\>Unregister-AzureRmAutomationScheduledRunbook -AutomationAccountName "Contoso17" -Name "Runbk01" -ResourceGroupName "ResourceGroup01" -ScheduleName "Runbk01Sched"
```

This command removes the association between the runbook named Runbk01 and the schedule named Runbk01Sched.

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

### -JobScheduleId
Specifies the ID of a scheduled runbook.

```yaml
Type: Guid]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for the scheduled runbook.

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
Specifies the name of the runbook that this cmdlet dissociates from a schedule.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleName
Specifies the name of the schedule from which this cmdlet dissociates a runbook.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
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

[Get-AzureRmAutomationScheduledRunbook](cfac4e12-2a1f-4b2c-873b-f5a3f9c4a2ce)

[Register-AzureRmAutomationScheduledRunbook](34edfa3b-7ef9-4aab-bb17-5ea725a22ed4)

