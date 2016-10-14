---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsJob.md
schema: 2.0.0
---

# Remove-AzureStreamAnalyticsJob

## SYNOPSIS
Asynchronously removes a specific Stream Analytics job in Microsoft Azure.

## SYNTAX

```
Remove-AzureStreamAnalyticsJob [-Name] <String> [-Force] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStreamAnalyticsJob** cmdlet asynchronously removes a specific Azure Stream Analytics job.
If you specify the *Force* parameter the job is deleted without confirmation.

## EXAMPLES

### Example 1: Remove a job
```
PS C:\>Remove-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -Name "StreamingJob" -Force
```

This command removes the job named StreamingJob, and does not prompt you for confirmation.

## PARAMETERS

### -Name
Specifies the name of the Azure Stream Analytics job to remove.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -ResourceGroupName
Specifies the name of the resource group that contains the job to remove.

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

[Start-AzureStreamAnalyticsJob](.\Start-AzureStreamAnalyticsJob.md)

[Stop-AzureStreamAnalyticsJob](.\Stop-AzureStreamAnalyticsJob.md)

