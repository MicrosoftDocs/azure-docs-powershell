---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-AlertHistory.md
schema: 2.0.0
---

# Add-AlertRule

## SYNOPSIS
Adds or updates an alert rule.

## SYNTAX

### Parameters for AddAlert cmdlet for events
```
Add-AlertRule -Operator <ConditionOperator> -Threshold <Double> -ResourceId <String> -EventName <String>
 -EventSource <String> -Level <String> -OperationName <String> -ResourceProvider <String> -Status <String>
 -SubStatus <String> [-EmailAddress <String>] -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for AddAlert cmdlet for metrics
```
Add-AlertRule -Operator <ConditionOperator> -Threshold <Double> -ResourceId <String> -MetricName <String>
 [-TimeAggregationOperator <TimeAggregationOperator>] -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for AddAlert cmdlet for webtests
```
Add-AlertRule -FailedLocationCount <Int32> -RuleType <AlertRuleTypes> -Location <String>
 [-Description <String>] [-DisableRule] -ResourceGroup <String> -Name <String> [-WindowSize <TimeSpan>]
 [-SendToServiceOwners] [-CustomEmails <String[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AlertRule** cmdlet adds or updates an alert rule for a resource group.
There are three types of alert rules: Metric, Event, and Webtest.

## EXAMPLES

### Example 1: Add a metric-based rule to a Web site
```
PS C:\>Add-AlertRule -RuleType Metric -Name "Web Metric 07" -Location "East US" -ResourceGroup "Default-Web-EastUS" -Operator GreaterThan -Threshold 2 -WindowSize 00:05:00 -ResourceId "/subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -MetricName "Requests" -Description "Metric rule for the site" -TimeAggregationOperator Total
RequestId                                                            StatusCode
---------                                                            ----------
33574ccf-0b01-43b4-aa97-87e6bbcf1c11                                    Created
```

This command creates a metric alert rule that is attached to the specified Web site.

### Example 2: Add a disabled rule or disable a rule
```
PS C:\>Add-AlertRule -RuleType Metric -Name "ContosoMetrics08" -Location "East US" -ResourceGroup "Default-Web-EastUS" -Operator GreaterThan -Threshold 2 -WindowSize 00:05:00 -ResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -MetricName Requests -TimeAggregationOperator Total -CustomEmail "ElisaDaugherty@Contoso.com" -SendToServiceOwners -Disable
RequestId                                                            StatusCode
---------                                                            ----------
96c489f1-8529-46e1-a76d-2c1463ca3116                                         OK
```

This command adds a disabled rule.
The command specifies the *Disabled* parameter, and so, if there is an existing rule named ContosoMetrics to update, this command disables that rule.
If there is no existing rule, this command adds the rule as disabled.

### Example 3: Create a metric-based rule that includes notification addresses
```
PS C:\>Add-AlertRule -Name "ContosoMetrics14" -Location "East US" -ResourceGroup "Default-Web-EastUS" -Operator GreaterThan -Threshold 1 -ResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -MetricName Requests -TimeAggregationOperator Total -CustomEmail "ElisaDaugherty@Contoso.com","DavidChew@Contoso.com"
RequestId                                                            StatusCode
---------                                                            ----------
9a5bc388-c7ac-4dc6-aa70-f4bc29c2c712                                         OK
```

This command creates a metric alert rule attached to a Web site.
The rule includes email addresses to receive notifications.

## PARAMETERS

### -Operator
Specifies a relational operator for the condition in the rule that this cmdlet adds or modifies.
Valid values are:

- GreaterThan 
- GreaterThanOrEqual 
- LessThan 
- LessThanOrEqual

```yaml
Type: ConditionOperator
Parameter Sets: Parameters for AddAlert cmdlet for events, Parameters for AddAlert cmdlet for metrics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Threshold
Specifies the threshold of the rule that this cmdlet adds or modifies.

```yaml
Type: Double
Parameter Sets: Parameters for AddAlert cmdlet for events, Parameters for AddAlert cmdlet for metrics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the resource that this rule monitors.

```yaml
Type: String
Parameter Sets: Parameters for AddAlert cmdlet for events, Parameters for AddAlert cmdlet for metrics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricName
Specifies the name of the metric that this rule monitors.
Specify this parameter for metric-based rules only.

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

### -TimeAggregationOperator
Specifies the aggregation operator to apply to the time window when the rule is evaluated.
Valid values are: 

- Average 
- Maximum 
- Minimum 
- Total

```yaml
Type: TimeAggregationOperator
Parameter Sets: Parameters for AddAlert cmdlet for metrics
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RuleType
Specifies the type of rule that this cmdlet adds or modifies.
Valid values are: 

- Metric 
- Event 
- Webtest

```yaml
Type: AlertRuleTypes
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location in which to define the rule.

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

### -Description
Specifies a description for the rule.

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
Indicates that this cmdlet adds the rule as disabled.
By default, rules are enabled.

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

### -ResourceGroup
Specifies the name of a resource group to which the rule applies.

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

### -Name
Specifies the name of the rule that this cmdlet adds or modifies.

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

### -WindowSize
Specifies the size of time window size, as a **TimeSpan**, in which the rule computes data.
For more information, type `Get-Help New-TimeSpan`.

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

### -SendToServiceOwners
Indicates that the rule to sends a notification to the service owners when the rule raises an alert.

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

### -CustomEmails
Specifies an array of email addresses.
When the rule raises an alert, it notifies customers at the addresses that this parameter specifies.

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

### -EventName
Specifies the name of the event that this rule monitors.
Specify this parameter for event-based rules only.

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
Specifies the source of the event that this rule monitors.
Specify this parameter for event-based rules only.

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

### -Level
Specifies the level of the event that this rule monitors.
Specify this parameter for event-based rules only.

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

### -OperationName
Specifies the name of an operation in the rule that this cmdlet adds or modifies.

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

### -ResourceProvider
Specifies the resource provider for the rule that this cmdlet adds or modifies.

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

### -Status
Specifies the status for the rule that this cmdlet adds or modifies.

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
Specifies the substatus.

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

### -EmailAddress
Specifies an email address.
When the rule becomes active, it notifies the person at the address that this parameter specifies.

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

### -FailedLocationCount
Specifies the failed location count for a Webtest rule.
The failed location count resembles the threshold in the other types of rules.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AlertHistory](.\Get-AlertHistory.md)

[Get-AlertRule](.\Get-AlertRule.md)

[Remove-AlertRule](.\Remove-AlertRule.md)

