---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Get-AzsStorageShareMetric

## SYNOPSIS
Gets the metrics of a specified share.

## SYNTAX

```
Get-AzsStorageShareMetric -ShareName <String> [-TimeGrain <TimeGrain>] [-StartTimeInUtc <DateTime>]
 [-EndTimeInUtc <DateTime>] [-MetricNames <String[]>] [-DetailedOutput] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Gets the metrics of a specified share.

## EXAMPLES

### Example 1
```
$shares = Get-AzsStorageShare

Get-AzsStorageShareMetric -ShareName $shares[0].ShareName
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
Indicates the cmdlet gets the detailed metric information from the Azs Share.

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
Specifies a string array of metric names that this cmdlet gets.

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

### -ShareName
Specifies the name of the Azs share that this cmdlet gets share metrics from.

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

[Get-AzsStorageShare](./Get-AzsStorageShare.md)

[Get-AzsStorageShareMetricDefinition](./Get-AzsStorageShareMetricDefinition.md)

