---
external help file: RMAzure_Automation.xml
online version: 73a4a9ba-477c-41e6-9193-2be97182e07d
schema: 2.0.0
---

# New-AzureRMAutomationSchedule
## SYNOPSIS
Creates an Automation schedule.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureRMAutomationSchedule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-StartTime] <DateTimeOffset> [-Description <String>] [-ExpiryTime <DateTimeOffset>] [-TimeZone <String>]
 -DayInterval <Byte>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureRMAutomationSchedule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-StartTime] <DateTimeOffset> [-Description <String>] [-TimeZone <String>] [-OneTime]
```

### UNNAMED_PARAMETER_SET_3
```
New-AzureRMAutomationSchedule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-StartTime] <DateTimeOffset> [-Description <String>] [-ExpiryTime <DateTimeOffset>] [-TimeZone <String>]
 -HourInterval <Byte>
```

### UNNAMED_PARAMETER_SET_4
```
New-AzureRMAutomationSchedule [-DayOfWeek <Nullable [System.DayOfWeek]>] [-DayOfWeekOccurrence]
 [-TimeZone <String>] -MonthInterval <Byte>
```

### UNNAMED_PARAMETER_SET_5
```
New-AzureRMAutomationSchedule [-DaysOfMonth <DaysOfMonth[]>] [-TimeZone <String>] -MonthInterval <Byte>
```

### UNNAMED_PARAMETER_SET_6
```
New-AzureRMAutomationSchedule [-DaysOfWeek <DayOfWeek[]>] [-TimeZone <String>] -WeekInterval <Byte>
```

## DESCRIPTION
The **New-AzureRmAutomationSchedule** cmdlet creates a schedule in azure_2 Automation.

## EXAMPLES

### Example 1: Create a one-time schedule in local time
```
PS C:\>$TimeZone = ([System.TimeZoneInfo]::Local)Id
PS C:\> New-AzureRmAutomationSchedule -AutomationAccountName "Contoso17" -Name "Schedule01" -StartTime "23:00" -OneTime -ResourceGroupName "ResourceGroup01" -TimeZone $TimeZone
```

The first command gets the time zone ID from the system and stores it in the $TimeZone variable.
The second command creates a schedule that runs one time on the current date at 11:00 PM in the specified time zone..

### Example 2: Create a recurring schedule
```
PS C:\>$StartTime = Get-Date "13:00:00"
PS C:\> $EndTime = $StartTime.AddYears(1)
PS C:\> New-AzureRmAutomationSchedule -AutomationAccountName "Contoso17" -Name "Schedule02" -StartTime $StartTime -ExpiryTime $EndTime -DailyInterval 1 -ResourceGroupName "ResourceGroup01"
```

The first command creates a date object by using the **Get-Date** cmdlet, and then stores the object in the $StartDate variable.
Specify a time that is at least five minutes in the future.

The second command creates a date object by using the **Get-Date** cmdlet, and then stores the object in the $EndDate variable.
The command specifies a future time.

The final command creates a daily schedule named Schedule01 to begin at the time stored in $StartDate and expire at the time stored in $EndDate.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet creates a schedule.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -DayInterval
Specifies an interval, in days, for the schedule.
If you do not specify this parameter, and you do not specify the *OneTime* parameter, the default value is one (1).

```yaml
Type: Byte
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DayOfWeek
Specifies a list of days of the week for the weekly schedule.

```yaml
Type: Nullable [System.DayOfWeek]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DayOfWeekOccurrence
Specifies the occurrence of the week within the month that the schedule runs.
psdx_paramvalues

-- 1
-- 2
-- 3
-- 4
-- -1
-- First
-- Second
-- Third
-- Fourth
-- LastDay

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 
Accepted values: First, Second, Third, Fourth, Last

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfMonth
Specifies a list of days of the month for the monthly schedule.

```yaml
Type: DaysOfMonth[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Specifies a list of days of the week for the weekly schedule.

```yaml
Type: DayOfWeek[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the schedule.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ExpiryTime
Specifies the expiry time of a schedule as a **DateTimeOffest** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.

```yaml
Type: DateTimeOffset
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HourInterval
Specifies an interval, in hours, for the schedule.

```yaml
Type: Byte
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthInterval
Specifies an interval, in Months, for the schedule.

```yaml
Type: Byte
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the schedule.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -OneTime
Specifies that the cmdlet creates a one-time schedule.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet creates a schedule.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time of a schedule as a **DateTimeOffset** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.
. If the *TimeZone* parameter is specified, the offset will be ignored and the time zone specified is used.

```yaml
Type: DateTimeOffset
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -TimeZone
Specifies the time zone for the schedule.
This string can be the IANA ID or the Windows Time Zone ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -WeekInterval
Specifies an interval, in weeks, for the schedule.

```yaml
Type: Byte
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Schedule

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationSchedule](73a4a9ba-477c-41e6-9193-2be97182e07d)

[Remove-AzureRmAutomationSchedule](633c3e61-0da0-4a01-897b-e81c6e571196)

[Set-AzureRmAutomationSchedule](2d34dc26-ead0-49f0-9e1a-9d4a81712616)

