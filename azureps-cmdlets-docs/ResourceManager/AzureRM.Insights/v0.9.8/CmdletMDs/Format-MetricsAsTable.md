---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-Metrics.md
schema: 2.0.0
---

# Format-MetricsAsTable

## SYNOPSIS
Formats metrics as an array of records.

## SYNTAX

```
Format-MetricsAsTable [-Metrics] <Metric[]> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Format-MetricsAsTable** cmdlet formats the output of the Get-Metrics cmdlet as an array of records.
This cmdlet creates one record for each metric value.
You can pass the output of this cmdlet to the **Export-Csv** cmdlet to create a comma separated value (.csv) file.
For more information, type `Get-Help Export-Csv`.

## EXAMPLES

### Example 1: Export formatted metrics
```
PS C:\>$Metrics = Get-Metrics -ResourceId "/subscriptions/b91eb07f-89c3-40be-bf3b-40fdcba10f6c/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite" -TimeGrain 00:01:00 -DetailedOutput
$Formatted = Format-MetricsAsTable -Metrics $Metrics
Foreach($Value in $Formatted) { Export-Csv -Path "./metrics.csv" -Input $Value -Append -NoTypeInformation }
"Name","TimestampUTC","Count","Last","Maximum","Minimum","Total","Average","StartTimeUTC","EndTimeUTC","TimeGrain","Unit","DimensionName","DimensionValue","ResourceId"
"AverageResponseTime","2015-03-20 16:15:00","1",,,,"0","0","2015-03-20 16:14:00","2015-03-20 17:14:35","00:01:00","Seconds",,,"/subscriptions/b91eb07f-89c3-40be-bf3b-40fdcba10f6c/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite"
"AverageResponseTime","2015-03-20 16:17:00","1",,,,"0","0","2015-03-20 16:14:00","2015-03-20 17:14:35","00:01:00","Seconds",,,"/subscriptions/b91eb07f-89c3-40be-bf3b-40fdcba10f6c/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite"
"AverageResponseTime","2015-03-20 16:18:00","1",,,,"0","0","2015-03-20 16:14:00","2015-03-20 17:14:35","00:01:00","Seconds",,,"/subscriptions/b91eb07f-89c3-40be-bf3b-40fdcba10f6c/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contososite"
```

The first command gets metrics for a resource ID by using the **Get-Metrics** cmdlet.
The command stores the results in the $Metrics array.

The second command uses the current cmdlet to format the metrics in $Metrics, and stores the formatted metrics in the $Formatted array.

The final command exports the contents of $Formatted to the file that is named metrics.csv by using **Export-Csv**.
The command uses the **Foreach**Windows PowerShell keyword.
For more information, type `Get-Help about_Foreach`.
The output of the example shows the exported data.

## PARAMETERS

### -Metrics
Specifies an array of **Metric** objects that this cmdlet formats.
To obtain **Metric** objects, use the **Get-Metrics** cmdlet.

```yaml
Type: Metric[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

