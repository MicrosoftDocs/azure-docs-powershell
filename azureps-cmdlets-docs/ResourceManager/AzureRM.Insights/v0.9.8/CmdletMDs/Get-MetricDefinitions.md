---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-Metrics.md
schema: 2.0.0
---

# Get-MetricDefinitions

## SYNOPSIS
Retrieves metric definitions.

## SYNTAX

```
Get-MetricDefinitions [-ResourceId] <String> [-MetricNames <String[]>] [-DetailedOutput]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MetricDefinitions** cmdlet retrieves metric definitions for a resource ID.

## EXAMPLES

### Example 1: Get metric definitions for a resource
```
PS C:\>Get-MetricDefinitions -ResourceId "/subscriptions/d33fb0c7-69d3-40be-e35b-4f0deba70fff/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosoweb02"
Name                   : CpuTime
Dimensions             : {}
MetricAvailabilities   : {Microsoft.Azure.Insights.Models.MetricAvailability, 
                         Microsoft.Azure.Insights.Models.MetricAvailability, 
                         Microsoft.Azure.Insights.Models.MetricAvailability}
PrimaryAggregationType : Total
Properties             : {}
ResourceUri            : 
Unit                   : Seconds

Name                   : Requests
Dimensions             : {}
MetricAvailabilities   : {Microsoft.Azure.Insights.Models.MetricAvailability, 
                         Microsoft.Azure.Insights.Models.MetricAvailability, 
                         Microsoft.Azure.Insights.Models.MetricAvailability}
PrimaryAggregationType : Total
Properties             : {}
ResourceUri            : 
Unit                   : Count
```

This command gets all definitions for the metrics in the resource specified by the resource ID.

### Example 2: Get details of metric definitions for a resource
```
PS C:\>Get-MetricDefinitions -ResourceId "/subscriptions/d33fb0c7-69d3-40be-e35b-4f0deba70fff/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite02" -DetailedOutput 
Dimensions             : 
MetricAvailabilities   : 
Location  : 
Retention : 2.00:00:00
Values    : 00:01:00
Location  :
Retention : 30.00:00:00
Values    : 01:00:00
Location  : 
Retention : 90.00:00:00
Values    : 1.00:00:00
Name                   : CpuTime
Properties             : 
PrimaryAggregationType : Total
ResourceUri            : 
Unit                   : Seconds

Dimensions             : 
MetricAvailabilities   : 
Location  : 
Retention : 2.00:00:00
Values    : 00:01:00
Location  : 
Retention : 30.00:00:00
Values    : 01:00:00
Location  : 
Retention : 90.00:00:00
Values    : 1.00:00:00
Name                   : Requests
Properties             : 
PrimaryAggregationType : Total
ResourceUri            : 
Unit                   : Count
```

This command gets all definitions for the metrics in the resource specified by the resource ID.
This command returns detailed information about the objects that it retrieves.

### Example 3: Get details of specific metric definitions for a resource
```
PS C:\>Get-MetricDefinitions -ResourceId "/subscriptions/d33fb0c7-69d3-40be-e35b-4f0deba70fff/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite02" -DetailedOutput -MetricNames "BytesSent","CpuTime"
Dimensions             : 
MetricAvailabilities   : 
Location  : 
Retention : 2.00:00:00
Values    : 00:01:00
Location  : 
Retention : 30.00:00:00
Values    : 01:00:00
Location  : 
Retention : 90.00:00:00
Values    : 1.00:00:00
Name                   : CpuTime
Properties             : 
PrimaryAggregationType : Total
ResourceUri            : 
Unit                   : Seconds

Dimensions             : 
MetricAvailabilities   : 
Location  : 
Retention : 2.00:00:00
Values    : 00:01:00
Location  : 
Retention : 30.00:00:00
Values    : 01:00:00
Location  : 
Retention : 90.00:00:00
Values    : 1.00:00:00
Name                   : BytesSent
Properties             : 
PrimaryAggregationType : Total
ResourceUri            : 
Unit                   : Bytes
```

This command gets definitions for two specified metrics in the resource specified by the resource ID.
This command returns detailed information about the objects that it retrieves.

## PARAMETERS

### -ResourceId
Specifies the resource ID of the resource associated with the metrics for which this cmdlet gets definitions.

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

### -MetricNames
Specifies an array of names of metrics.
This cmdlet retrieves definitions for the metrics that this parameter specifies.

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

[Get-Metrics](.\Get-Metrics.md)

