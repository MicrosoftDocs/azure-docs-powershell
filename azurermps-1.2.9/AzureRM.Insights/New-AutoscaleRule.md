---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AutoscaleRule

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

```
New-AutoscaleRule -MetricName <String> -MetricResourceId <String> -Operator <ComparisonOperationType>
 -MetricStatistic <MetricStatisticType> -Threshold <Double> [-TimeAggregationOperator <TimeAggregationType>]
 -TimeGrain <TimeSpan> [-TimeWindow <TimeSpan>] -ScaleActionCooldown <TimeSpan>
 -ScaleActionDirection <ScaleDirection> -ScaleActionScaleType <ScaleType> -ScaleActionValue <String>
 [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -MetricName
The metric name for the setting

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

### -MetricResourceId
The metric resource id for the setting

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

### -MetricStatistic
The setting metric statistic

```yaml
Type: MetricStatisticType
Parameter Sets: (All)
Aliases: 
Accepted values: Average, Min, Max, Sum

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operator
The setting condition operator

```yaml
Type: ComparisonOperationType
Parameter Sets: (All)
Aliases: 
Accepted values: Equals, NotEquals, GreaterThan, GreaterThanOrEqual, LessThan, LessThanOrEqual

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleActionCooldown
The scale action cooldown time for the setting

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleActionDirection
The acale action direction for the setting

```yaml
Type: ScaleDirection
Parameter Sets: (All)
Aliases: 
Accepted values: None, Increase, Decrease

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleActionScaleType
The scale action type for the setting

```yaml
Type: ScaleType
Parameter Sets: (All)
Aliases: 
Accepted values: ChangeSize, ChangeCount, PercentChangeCount, ExactCount

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleActionValue
The scale action value for the setting

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

### -Threshold
The threshold for the setting condition

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeAggregationOperator
The time aggregation operator for the setting

```yaml
Type: TimeAggregationType
Parameter Sets: (All)
Aliases: 
Accepted values: Average, Minimum, Maximum, Last, Total, Count

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeGrain
The metric trigger time grain for the setting

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeWindow
The metric trigger timewindow for the setting

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Management.Insights.Models.ComparisonOperationType
Microsoft.Azure.Management.Insights.Models.MetricStatisticType
System.Double
Microsoft.Azure.Management.Insights.Models.TimeAggregationType
System.TimeSpan
Microsoft.Azure.Management.Insights.Models.ScaleDirection
Microsoft.Azure.Management.Insights.Models.ScaleType

## OUTPUTS

### Microsoft.Azure.Management.Insights.Models.ScaleRule

## NOTES

## RELATED LINKS

