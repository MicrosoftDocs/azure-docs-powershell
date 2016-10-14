---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Format-MetricsAsTable.md
schema: 2.0.0
---

# Get-UsageMetrics

## SYNOPSIS
Retrieves usage metric values of a resource.

## SYNTAX

```
Get-UsageMetrics [-ResourceId] <String> [-ApiVersion <String>] [-StartTime <DateTime>] [-EndTime <DateTime>]
 [-MetricNames <String[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UsageMetrics** cmdlet retrieves usage metric values of a resource.

## EXAMPLES

### Example 1: Get usage metric values
```
PS C:\>Get-UsageMetrics -ResourceId "/subscriptions/bcdeb07f-1c43-20be-1f3b-4f0febc10f5b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/evannarvaez"
```

This command gets the usage metric values for a website.

## PARAMETERS

### -ResourceId
Specifies a resource ID.
This cmdlet gets values for usage metrics that are associated to the resource that this parameter specifies.

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

### -ApiVersion
Specifies the API version string for the resource for which this cmdlet gets usage metric values.
The default value is any API version string.

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

### -StartTime
Specifies the start time, as a **DateTime** object, for the usage metric values that this cmdlet gets.

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
Specifies the end time, as a **DateTime** object, for the usage metric values that this cmdlet gets.
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
Specifies an array of names of metrics for which this cmdlet gets usage metric values.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Format-MetricsAsTable](.\Format-MetricsAsTable.md)

