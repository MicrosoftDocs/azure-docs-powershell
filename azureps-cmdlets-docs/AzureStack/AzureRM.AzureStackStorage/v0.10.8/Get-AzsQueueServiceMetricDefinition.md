---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzsQueueServiceMetricDefinition

## SYNOPSIS
Gets the metric definition properties exposed by the Queue service.

## SYNTAX

```
Get-AzsQueueServiceMetricDefinition [-MetricNames <String[]>] [-DetailedOutput] [-SkipCertificateValidation]
```

## DESCRIPTION
The **Get-AzsQueueServiceMetricDefinition** cmdlet gets the metric definitions of the Queue service.

## EXAMPLES
### Example 1

```
Get-AzsQueueServiceMetricDefinition -DetailedOutput | Format-Table -Wrap 
```

## PARAMETERS

### -DetailedOutput
Indicates the cmdlet gets the detailed metric information from the Azs Queue service definition.

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

### -MetricNames
Specifies an array of metric names in which this cmdlet gets definitions from.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## RELATED LINKS

[Get-AzsQueueService](./Get-AzsBlobService.md)

[Get-AzsQueueServiceMetric](./Get-AzsBlobServiceMetric.md)


