---
external help file: RMAzure_Automation.xml
online version: 36c11dd3-5843-49d2-8baa-9f5aa737d345
schema: 2.0.0
---

# Get-AzureRMAutomationSchedule
## SYNOPSIS
Gets an Automation schedule.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationSchedule [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationSchedule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationSchedule** cmdlet gets an azure_2 Automation schedule.

## EXAMPLES

### Example 1: Get a schedule
```
PS C:\>Get-AzureRmAutomationSchedule -AutomationAccountName "Contoso17" -Name "DailySchedule08" -ResourceGroupName "ResourceGroup01"
```

This command gets the schedule named DailySchedule08.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet get a schedule.

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
Specifies the name of a schedule that this cmdlet gets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ScheduleName

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet gets a schedule.

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

### Microsoft.Azure.Commands.Automation.Model.Schedule

## NOTES

## RELATED LINKS

[New-AzureRmAutomationSchedule](36c11dd3-5843-49d2-8baa-9f5aa737d345)

[Remove-AzureRmAutomationSchedule](633c3e61-0da0-4a01-897b-e81c6e571196)

[Set-AzureRmAutomationSchedule](2d34dc26-ead0-49f0-9e1a-9d4a81712616)

