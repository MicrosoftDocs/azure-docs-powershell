---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsJob.md
schema: 2.0.0
---

# Start-AzureStreamAnalyticsJob

## SYNOPSIS
Asynchronously deploys and starts a Stream Analytics job in Microsoft Azure.

## SYNTAX

```
Start-AzureStreamAnalyticsJob [-Name] <String> [[-OutputStartMode] <String>] [[-OutputStartTime] <DateTime>]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureStreamAnalyticsJob** cmdlet asynchronously deploys and starts a Stream Analytics job in Microsoft Azure.

## EXAMPLES

### Example 1: Deploy and start a job
```
PS C:\>Start-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -Name "StreamingJob" -OutputStartMode "CustomTime" -OutputStartTime 2014-07-03T01:00Z
```

This command starts the job named StreamingJob and specifies that the output event stream should start at timestamp 2014-07-03T01:00Z.

## PARAMETERS

### -Name
Specifies the name of the job to start.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputStartMode
Specifies the starting point of the output event stream.
The acceptable values for this parameter are:

- JobStartTime.
Starts the output event stream when the job starts.
- CustomTime.
Starts the output event stream at the time specified by the *OutputStartTime* parameter.
- LastOutputEventTime.
Starts the output event stream from the last output event time.

The default value for this parameter is JobStartTime.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputStartTime
Specifies a time stamp, in ISO-8601 format, to indicate the starting point of the output event stream, or Null to start that the output event stream when the streaming job starts.

You must specify a value for this parameter if the *OutputStartMode* parameter is set to CustomTime.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that the Azure Stream Analytics job belongs to.

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

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

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

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsJob](.\Get-AzureStreamAnalyticsJob.md)

[New-AzureStreamAnalyticsJob](.\New-AzureStreamAnalyticsJob.md)

[Remove-AzureStreamAnalyticsJob](.\Remove-AzureStreamAnalyticsJob.md)

[Stop-AzureStreamAnalyticsJob](.\Stop-AzureStreamAnalyticsJob.md)

