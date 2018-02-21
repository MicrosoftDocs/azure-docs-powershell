---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Get-AzsStorageFarmMetric

## SYNOPSIS
Gets the metrics for a specified storage farm.

## SYNTAX

```
Get-AzsStorageFarmMetric [-TimeGrain <TimeGrain>] [-StartTimeInUtc <DateTime>] [-EndTimeInUtc <DateTime>]
 [-MetricNames <String[]>] [-DetailedOutput] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzsStorageFarmMetric** cmdlet gets the metrics for a specified storage farm.

## EXAMPLES

### Example 1
```
$Metrics = Get-AzsStorageFarmMetricDefinition

$MetricNames = $Metrics.Name

Get-AzsStorageFarmMetric -TimeGrain Daily -StartTimeInUtc 7/4/2017 -EndTimeInUtc 7/5/2017 -MetricNames $MetricNames[2]
```

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DetailedOutput
Indicates that the cmdlet gets detailed information from the output.

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

### -EndTimeInUtc
Specifies the endtime of the duration for the collected metrics

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
Specifies an array of metric names that this cmdlet gets.

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

### -SkipCertificateValidation
Indicates that the cmdlet does not validate the certificate.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTimeInUtc
Specifies the starttime of the duration for the collected metrics

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

### -TimeGrain
Specifies the aggregation precision of the metrics. Valid values are: Daily, Hourly, and Minutely. The default value is Daily.

```yaml
Type: TimeGrain
Parameter Sets: (All)
Aliases: 
Accepted values: Daily, Hourly, Minutely

Required: False
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

[Get-AzsStorageFarmMetricDefinition](./Get-AzsStorageFarmMetricDefinition.md)


