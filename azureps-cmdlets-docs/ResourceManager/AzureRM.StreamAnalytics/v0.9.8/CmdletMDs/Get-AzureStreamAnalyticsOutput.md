---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\New-AzureStreamAnalyticsOutput.md
schema: 2.0.0
---

# Get-AzureStreamAnalyticsOutput

## SYNOPSIS
Lists all of the outputs that are defined in a specified Stream Analytics job or gets information about a specific output.

## SYNTAX

```
Get-AzureStreamAnalyticsOutput [-JobName] <String> [[-Name] <String>] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStreamAnalyticsOutput** cmdlet lists all of the outputs that are defined in a specified Stream Analytics job or gets information about a specific output.

## EXAMPLES

### Example 1: Get all outputs for a job
```
PS C:\>Get-AzureStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob"
```

This command gets all of the outputs that are defined for the job named StreamingJob.

### Example 2: Get a specified output for a job
```
PS C:\>Get-AzureStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -Name "Output"
```

This command gets the output named Output that is defined for the job named StreamingJob.

## PARAMETERS

### -JobName
Specifies the name of the Azure Stream Analytics job that the desired Azure Stream Analytics output belongs to.

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

### -Name
Specifies the name of the Azure Stream Analytics output to retrieve.

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

### -ResourceGroupName
Specifies the name of the resource group that the Azure Stream Analytics output belongs to.

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

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.StreamAnalytics.Models.PSOutput, Microsoft.Azure.Commands.StreamAnalytics, Version=0.8.11.0, Culture=neutral, PublicKeyToken=null]]Microsoft.Azure.Commands.StreamAnalytics.Models.PSOutput

## NOTES

## RELATED LINKS

[New-AzureStreamAnalyticsOutput](.\New-AzureStreamAnalyticsOutput.md)

[Remove-AzureStreamAnalyticsOutput](.\Remove-AzureStreamAnalyticsOutput.md)

[Test-AzureStreamAnalyticsOutput](.\Test-AzureStreamAnalyticsOutput.md)

