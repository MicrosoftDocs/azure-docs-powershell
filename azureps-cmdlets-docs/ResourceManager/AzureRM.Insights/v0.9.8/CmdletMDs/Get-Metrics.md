---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-MetricDefinitions.md
schema: 2.0.0
---

# Get-Metrics

## SYNOPSIS
Retrieves metric values of a resource.

## SYNTAX

```
Get-Metrics [-ResourceId] <String> [-TimeGrain] <TimeSpan> [-StartTime <DateTime>] [-EndTime <DateTime>]
 [-MetricNames <String[]>] [-DetailedOutput] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Metrics** cmdlet retrieves metric values of a resource.
You can specify which values to get.

## EXAMPLES

### Example 1: Get metric values for a web site
```
PS C:\>Get-Metrics -ResourceId "/subscriptions/e3f5b07d-3c39-4b0f-bf3b-40fdeba10f2a/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb03" -TimeGrain 00:01:00
DimensionName  : 
DimensionValue : 
Name           : AverageResponseTime
EndTime        : 3/20/2015 6:40:46 PM
MetricValues   : {Microsoft.Azure.Insights.Models.MetricValue, Microsoft.Azure.Insights.Models.MetricValue, 
                 Microsoft.Azure.Insights.Models.MetricValue, Microsoft.Azure.Insights.Models.MetricValue...} 
Properties     : {}
ResourceId     : /subscriptions/e3f5b07d-3c39-4b0f-bf3b-40fdeba10f2a/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb03
StartTime      : 3/20/2015 5:40:00 PM
TimeGrain      : 00:01:00
Unit           : Seconds

DimensionName  : 
DimensionValue : 
Name           : AverageMemoryWorkingSet
EndTime        : 3/20/2015 6:40:46 PM
MetricValues   : {Microsoft.Azure.Insights.Models.MetricValue, Microsoft.Azure.Insights.Models.MetricValue, 
                 Microsoft.Azure.Insights.Models.MetricValue, Microsoft.Azure.Insights.Models.MetricValue...} 
Properties     : {}
ResourceId     : /subscriptions/e3f5b07d-3c39-4b0f-bf3b-40fdeba10f2a/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb03
StartTime      : 3/20/2015 5:40:00 PM
TimeGrain      : 00:01:00
Unit           : Bytes
```

This command gets the metric values for contosoweb03.
The command specifies a time grain of one minute.

### Example 2: Get detailed metric values for a web site
```
PS C:\>Get-Metrics -ResourceId "/subscriptions/e3f5b07d-3c39-4b0f-bf3b-40fdeba10f2a/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb03" -TimeGrain 00:01:00 -DetailedOutput
MetricValues   : 
Average    : 0
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:37:00 PM
Total      : 0
Average    : 0.106
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:39:00 PM
Total      : 0.106
Average    : 0.064
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:41:00 PM
Total      : 0.064
Properties     : 
DimensionName  : 
DimensionValue : 
Name           : AverageResponseTime
EndTime        : 3/20/2015 6:43:33 PM
ResourceId     : /subscriptions/e3f5b07d-3c39-4b0f- . . . eb/sites/contosoweb03 
StartTime      : 3/20/2015 5:43:00 PM
TimeGrain      : 00:01:00
Unit           : Seconds
```

This command gets the metric values for contosoweb03.
The command specifies a time grain of one minute.
This command displays detailed output.

### Example 3: Get details of values for named metrics for a web site
```
PS C:\>Get-Metrics -ResourceId "/subscriptions/e3f5b07d-3c39-4b0f-bf3b-40fdeba10f2a/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb03" -TimeGrain 00:01:00 -DetailedOutput -MetricNames Requests
MetricValues   : 
Average    : 1
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:39:00 PM
Total      : 1
Average    : 1
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:41:00 PM
Total      : 1
Average    : 0
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:43:00 PM
Total      : 0
Average    : 1
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:44:00 PM
Total      : 1
Average    : 0
Count      : 1
Last       : 
Maximum    : 
Minimum    : 
Properties : 
Timestamp  : 3/20/2015 6:45:00 PM
Total      : 0
Properties     : 
DimensionName  : 
DimensionValue : 
Name           : Requests
EndTime        : 3/20/2015 6:47:56 PM
ResourceId     : /subscriptions/e3f5b07d-3c39-4b0f- . . . eb/sites/contosoweb03
StartTime      : 3/20/2015 5:47:00 PM
TimeGrain      : 00:01:00
Unit           : Count
```

This command gets the metric values for metrics named Requests for contosoweb03.
The command specifies a time grain of one minute.
This command displays detailed output.

## PARAMETERS

### -ResourceId
Specifies a resource ID.
This cmdlet gets values for metrics that are associated to the resource that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeGrain
Specifies the time grain, as a **TimeSpan**, of the metric that this cmdlet gets.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time, as a **DateTime** object, for the metric values that this cmdlet gets.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the end time, as a **DateTime** object, for the metric values that this cmdlet gets.
For more information about **DateTime**, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricNames
Specifies an array of names of metrics for which this cmdlet gets values.

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

### -DetailedOutput
Indicates that this cmdlet displays detailed information about the objects that it retrieves.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MetricDefinitions](.\Get-MetricDefinitions.md)

[Format-MetricsAsTable](.\Format-MetricsAsTable.md)

