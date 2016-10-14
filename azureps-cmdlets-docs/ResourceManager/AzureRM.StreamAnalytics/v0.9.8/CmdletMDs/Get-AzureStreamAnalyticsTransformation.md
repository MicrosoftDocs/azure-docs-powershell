---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\New-AzureStreamAnalyticsTransformation.md
schema: 2.0.0
---

# Get-AzureStreamAnalyticsTransformation

## SYNOPSIS
Gets information about a specific transformation defined on a Stream Analytics job.

## SYNTAX

```
Get-AzureStreamAnalyticsTransformation [-JobName] <String> [-Name] <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStreamAnalyticsTransformation** cmdlet gets information about a specific transformation defined on Stream Analytics job.

## EXAMPLES

### Example 1: Get a transformation
```
PS C:\>Get-AzureStreamAnalyticsTransformation -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -Name "StreamingTransformation"
```

This command gets the transformation named StreamingTransformation that is defined for the job named StreamingJob.

## PARAMETERS

### -JobName
Specifies the name of the Azure Stream Analytics job that the desired Azure Stream Analytics transformation belongs to.

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
Specifies the name of the transformation to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the transformation to get.

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

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.StreamAnalytics.Models.PSTransformation, Microsoft.Azure.Commands.StreamAnalytics, Version=0.8.11.0, Culture=neutral, PublicKeyToken=null]]Microsoft.Azure.Commands.StreamAnalytics.Models.PSTransformation

## NOTES

## RELATED LINKS

[New-AzureStreamAnalyticsTransformation](.\New-AzureStreamAnalyticsTransformation.md)

