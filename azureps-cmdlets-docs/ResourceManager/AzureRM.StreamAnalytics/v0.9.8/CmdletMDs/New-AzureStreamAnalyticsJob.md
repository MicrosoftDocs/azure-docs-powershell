---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsJob.md
schema: 2.0.0
---

# New-AzureStreamAnalyticsJob

## SYNOPSIS
Creates a Stream Analytics job in Azure or updates the definition of an existing specified job.

## SYNTAX

```
New-AzureStreamAnalyticsJob [[-Name] <String>] [-File] <String> [-Force] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStreamAnalyticsJob** cmdlet creates a new Stream Analytics job in Microsoft Azure or updates the definition of an existing specified job.
The name of the job can be specified in the .JSON file or on the command line.
If both are specified, the name on command line must be the same with the one in the file.
If you specify a job name that already exists and do not specify the *Force* parameter, the cmdlet prompts whether to replace the existing job.
If you specify the *Force* parameter and specify an existing job name, the job definition is replaced without confirmation.

## EXAMPLES

### Example 1: Create a job
```
PS C:\>New-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\JobDefinition.json"
```

This command creates a job from the definition in JobDefinition.json.
If an existing job with the name specified in the job definition file is already defined, the cmdlet prompts you whether to replace it.

### Example 2: Replace an existing job
```
PS C:\>New-AzureStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\JobDefinition.json" -Name "StreamingJob" -Force
```

This command replaces the job definition for the job named StreamingJob.

## PARAMETERS

### -Name
Specifies the name of the job to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -File
Specifies the path to a .JSON file that contains the definition of the job to create or replace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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
Specifies the name of the resource group in which to create or replace a job.

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

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSJob

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsJob](.\Get-AzureStreamAnalyticsJob.md)

[Remove-AzureStreamAnalyticsJob](.\Remove-AzureStreamAnalyticsJob.md)

[Start-AzureStreamAnalyticsJob](.\Start-AzureStreamAnalyticsJob.md)

[Stop-AzureStreamAnalyticsJob](.\Stop-AzureStreamAnalyticsJob.md)

