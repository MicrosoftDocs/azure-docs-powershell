---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\New-AzureStreamAnalyticsJob.md
schema: 2.0.0
---

# Get-AzureStreamAnalyticsJob

## SYNOPSIS
Lists all Stream Analytics jobs defined in the Azure subscription or specified resource group or gets job information about a specific job within a resource group.

## SYNTAX

### For stream analytics objects in the given resource group
```
Get-AzureStreamAnalyticsJob [-ResourceGroupName] <String> [[-Name] <String>] [-NoExpand]
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### For stream analytics objects in the given subscription
```
Get-AzureStreamAnalyticsJob [-NoExpand] [-Profile <AzureProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStreamAnalyticsJob** cmdlet gets all of the Stream Analytics jobs that are defined in an Azure subscription or specified resource group, or gets a specified job in a resource group.

## EXAMPLES

### Example 1: Get all of the jobs in a subscription
```
PS C:\>Get-AzureStreamAnalyticsJob
```

This command gets all of the Stream Analytics jobs in an Azure subscription.

### Example 2: Get all of the jobs in a resource group
```
PS C:\>Get-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US."
```

This command gets all of the Stream Analytics jobs in the resource group named StreamAnalytics-Default-West-US.

### Example 3: Get a specified job
```
PS C:\>Get-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -Name "StreamingJob"
```

This command gets the Stream Analytics job named StreamingJob in the resource group named StreamAnalytics-Default-West-US.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the resource group that the Azure Stream Analytics job belongs to.

```yaml
Type: String
Parameter Sets: For stream analytics objects in the given resource group
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the Azure Stream Analytics job to retrieve.

```yaml
Type: String
Parameter Sets: For stream analytics objects in the given resource group
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoExpand
Indicates that this cmdlet will retrieve the Azure Stream Analytics job, but not return information on its inputs, outputs, or transformation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.StreamAnalytics.Models.PSJob, Microsoft.Azure.Commands.StreamAnalytics, Version=0.8.11.0, Culture=neutral, PublicKeyToken=null]]Microsoft.Azure.Commands.StreamAnalytics.Models.PSJob

## NOTES

## RELATED LINKS

[New-AzureStreamAnalyticsJob](.\New-AzureStreamAnalyticsJob.md)

[Remove-AzureStreamAnalyticsJob](.\Remove-AzureStreamAnalyticsJob.md)

[Start-AzureStreamAnalyticsJob](.\Start-AzureStreamAnalyticsJob.md)

[Stop-AzureStreamAnalyticsJob](.\Stop-AzureStreamAnalyticsJob.md)

