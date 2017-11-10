---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AlertRule

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Parameters for AddAlert cmdlet for metrics
```
Add-AlertRule -Operator <ConditionOperator> -Threshold <Double> -ResourceId <String> -MetricName <String>
 [-TimeAggregationOperator <TimeAggregationOperator>] -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [<CommonParameters>]
```

### Parameters for AddAlert cmdlet for events
```
Add-AlertRule -Operator <ConditionOperator> -Threshold <Double> -ResourceId <String> -EventName <String>
 -EventSource <String> -Level <String> -OperationName <String> -ResourceProvider <String> -Status <String>
 -SubStatus <String> [-EmailAddress <String>] -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [<CommonParameters>]
```

### Parameters for AddAlert cmdlet for webtests
```
Add-AlertRule -FailedLocationCount <Int32> -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [<CommonParameters>]
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

### -CustomEmails
The list of custom e-mails

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
The rule description

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableRule
The disable rule (status) flag

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EmailAddress
The e-mail address for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventName
The event name for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventSource
The event source for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FailedLocationCount
The failed location count for rule

```yaml
Type: Int32
Parameter Sets: Parameters for AddAlert cmdlet for webtests
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Level
The level for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
The Location name

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

### -MetricName
The metric name for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for metrics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The alert rule name

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

### -OperationName
The operation name for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operator
The rule condition operator

```yaml
Type: ConditionOperator
Parameter Sets: Parameters for AddAlert cmdlet for metrics, Parameters for AddAlert cmdlet for events
Aliases: 
Accepted values: GreaterThan, GreaterThanOrEqual, LessThan, LessThanOrEqual

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
The resource group name

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

### -ResourceId
The resource id for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for metrics, Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceProvider
The resource provider for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RuleType
The rule type

```yaml
Type: AlertRuleTypes
Parameter Sets: (All)
Aliases: 
Accepted values: Metric, Event, Webtest

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SendToServiceOwners
The send to service owner flag

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
The status for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubStatus
The substatus for rule

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Threshold
The threshold for rule condition

```yaml
Type: Double
Parameter Sets: Parameters for AddAlert cmdlet for metrics, Parameters for AddAlert cmdlet for events
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeAggregationOperator
The time aggregation operator for rule

```yaml
Type: TimeAggregationOperator
Parameter Sets: Parameters for AddAlert cmdlet for metrics
Aliases: 
Accepted values: Average, Minimum, Maximum, Total, Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowSize
The window size for rule

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

### Microsoft.Azure.Management.Insights.Models.ConditionOperator
System.Double
System.String
System.Nullable`1[[Microsoft.Azure.Management.Insights.Models.TimeAggregationOperator, Microsoft.Azure.Insights, Version=0.9.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]
System.Int32
Microsoft.Azure.Commands.Insights.Alerts.AlertRuleTypes
System.Management.Automation.SwitchParameter
System.TimeSpan
System.String[]

## OUTPUTS

### System.Collections.Generic.List`1[[System.Management.Automation.PSObject, System.Management.Automation, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## NOTES

## RELATED LINKS

