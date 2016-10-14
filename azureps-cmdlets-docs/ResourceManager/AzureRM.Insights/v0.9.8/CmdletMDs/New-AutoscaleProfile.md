---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\New-AutoscaleRule.md
schema: 2.0.0
---

# New-AutoscaleProfile

## SYNOPSIS
Creates an Autoscale profile.

## SYNTAX

### Parameters for AddAutoscale profile cmdlet using recurrent scheduling
```
New-AutoscaleProfile -Name <String> -DefaultCapacity <String> -MaximumCapacity <String>
 -MinimumCapacity <String> -RecurrenceFrequency <RecurrenceFrequency>
 -ScheduleDays <System.Collections.Generic.List`1[System.String]>
 -ScheduleHours <System.Collections.Generic.List`1[System.Int32]>
 -ScheduleMinutes <System.Collections.Generic.List`1[System.Int32]> -ScheduleTimeZone <String>
 -Rules <System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.ScaleRule]>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for AddAutoscale profile cmdlet using fix date scheduling
```
New-AutoscaleProfile -Name <String> -DefaultCapacity <String> -MaximumCapacity <String>
 -MinimumCapacity <String> -StartTimeWindow <DateTime> -EndTimeWindow <DateTime> -TimeWindowTimeZone <String>
 -Rules <System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.ScaleRule]>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for AddAutoscale profile cmdlet without scheduled times
```
New-AutoscaleProfile -Name <String> -DefaultCapacity <String> -MaximumCapacity <String>
 -MinimumCapacity <String>
 -Rules <System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.ScaleRule]>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AutoscaleProfile** cmdlet creates an Autoscale profile.

## EXAMPLES

### Example 1: Create a profile with a fixed date
```
PS C:\>$Rule = New-AutoscaleRule -MetricName "Requests" -MetricResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -Operator GreaterThan -MetricStatistic Average -Threshold 10 -TimeGrain 00:01:00 -ScaleActionCooldown 00:05:00 -ScaleActionDirection Increase -ScaleActionScaleType ChangeCount -ScaleActionValue "1" 
PS C:\> $Profile = New-AutoscaleProfile -DefaultCapacity "1" -MaximumCapacity "10" -MinimumCapacity "1" -StartTimeWindow 2015-03-05T14:00:00 -EndTimeWindow 2015-03-05T14:30:00 -TimeWindowTimeZone GMT -Rules $Rule -Name "ContosoProfile"
Capacity   : Microsoft.Azure.Management.Insights.Models.ScaleCapacity
FixedDate  : Microsoft.Azure.Management.Insights.Models.TimeWindow
Name       : ContosoProfile
Recurrence : 
Rules      : {Microsoft.Azure.Management.Insights.Models.ScaleRule, 
             Microsoft.Azure.Management.Insights.Models.ScaleRule}
```

The first command creates an Autoscale rule, and then stores it in the $Rule variable.

The second command creates a profile that lacks a schedule, and then stores it in the $Profile variable.
The profile includes the rule stored in $Rule.

### Example 2: Create a profile with a schedule
```
PS C:\>$Rule = New-AutoscaleRule -MetricName Requests -MetricResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -Operator GreaterThan -MetricStatistic Average -Threshold 10 -TimeGrain 00:01:00 -ScaleActionCooldown 00:05:00 -ScaleActionDirection Increase -ScaleActionScaleType ChangeCount -ScaleActionValue "1" 
PS C:\> $Profile = New-AutoscaleProfile -DefaultCapacity "1" -MaximumCapacity "10" -MinimumCapacity "1" -Rules $Rule -Name "ContosoRecurrentProfile" -RecurrenceFrequency Minute -ScheduleDays "1", "2", "3" -ScheduleHours 5, 10, 15 -ScheduleMinutes 15, 30, 45 -ScheduleTimeZone GMT
Capacity   : Microsoft.Azure.Management.Insights.Models.ScaleCapacity
FixedDate  : 
Name       : ContosoRecurrentProfile
Recurrence : Microsoft.Azure.Management.Insights.Models.Recurrence
Rules      : {Microsoft.Azure.Management.Insights.Models.ScaleRule, 
             Microsoft.Azure.Management.Insights.Models.ScaleRule}
```

The first command creates an Autoscale rule, and then stores it in the $Rule variable.

The second command creates a profile that specifies a recurrent schedule, and then stores it in the $Profile variable.
The profile includes the rule stored in $Rule.

## PARAMETERS

### -Name
Specifies a name for the new profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultCapacity
Specifies the default capacity for the new profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumCapacity
Specifies the maximum capacity for the new profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumCapacity
Specifies the minimum capacity for the new profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecurrenceFrequency
Specifies the frequency of recurrence for the new profile.
Valid values are: 

- None 
- Second 
- Minute 
- Hour 
- Day 
- Week 
- Month 
- Year 

This cmdlet does not currently support all these values.

```yaml
Type: RecurrenceFrequency
Parameter Sets: Parameters for AddAutoscale profile cmdlet using recurrent scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleDays
Specifies an array of scheduled days that this cmdlet adds to the new profile.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Parameters for AddAutoscale profile cmdlet using recurrent scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleHours
Specifies an array of scheduled hours that this cmdlet adds to the new profile.

```yaml
Type: System.Collections.Generic.List`1[System.Int32]
Parameter Sets: Parameters for AddAutoscale profile cmdlet using recurrent scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleMinutes
Specifies an array of scheduled minutes that this cmdlet adds to the new profile.

```yaml
Type: System.Collections.Generic.List`1[System.Int32]
Parameter Sets: Parameters for AddAutoscale profile cmdlet using recurrent scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleTimeZone
Specifies the time zone of the schedule for the new profile.

```yaml
Type: String
Parameter Sets: Parameters for AddAutoscale profile cmdlet using recurrent scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rules
Specifies an array of rules that this cmdlet adds to the new profile.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.ScaleRule]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTimeWindow
Specifies the start, as a **DateTime** object, of the time window for the new profile.

```yaml
Type: DateTime
Parameter Sets: Parameters for AddAutoscale profile cmdlet using fix date scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTimeWindow
Specifies the end, as a **DateTime** object, of the time window for the new profile.
For more information about **DateTime**, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: Parameters for AddAutoscale profile cmdlet using fix date scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeWindowTimeZone
Specifies the time zone of the time window.

```yaml
Type: String
Parameter Sets: Parameters for AddAutoscale profile cmdlet using fix date scheduling
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AutoscaleRule](.\New-AutoscaleRule.md)

[Add-AutoscaleSetting](.\Add-AutoscaleSetting.md)

[Get-AutoscaleSetting](.\Get-AutoscaleSetting.md)

[Remove-AutoscaleSetting](.\Remove-AutoscaleSetting.md)

[Get-AutoscaleHistory](.\Get-AutoscaleHistory.md)

