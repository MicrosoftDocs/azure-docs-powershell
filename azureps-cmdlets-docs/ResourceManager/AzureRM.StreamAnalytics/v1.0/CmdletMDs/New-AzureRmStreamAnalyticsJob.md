---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureRmStreamAnalyticsJob.md
schema: 2.0.0
---

# New-AzureRmStreamAnalyticsJob

## SYNOPSIS
Creates or updates a Stream Analytics job.

## SYNTAX

```
New-AzureRmStreamAnalyticsJob [[-Name] <String>] [-File] <String> [-Force] [-ResourceGroupName] <String>
 [-PipelineVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmStreamAnalyticsJob** cmdlet creates a new Stream Analytics job in azure_2 or updates the definition of an existing specified job.
The name of the job can be specified in the .JSON file or on the command line.
If both are specified, the name on command line must match the name in the file.

If you specify a job name that already exists and do not specify the *Force* parameter, the cmdlet will ask whether or not to replace the existing job.

If you specify the *Force* parameter and specify an existing job name, the job definition will be replaced without confirmation.

## EXAMPLES

### EXAMPLE 1: Create a job
```
PS C:\>New-AzureRmStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\JobDefinition.json"
```

This command creates a job from the definition in JobDefinition.json.
If an existing job with the specified name in the job definition file is already defined, the cmdlet will ask whether or not to replace it.

### EXAMPLE 2: Replace a job definition
```
PS C:\>New-AzureRmStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\JobDefinition.json" -Name "StreamingJob" -Force
```

This command replaces the job definition for StreamingJob without confirmation.

## PARAMETERS

### -Name
Specifies the name of the azure_2 Stream Analytics job to create.

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
Specifies the path to a JSON file that contains the JSON representation of the azure_2 Stream Analytics job to create.

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
ps_force

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
Specifies the name of the resource group to which the azure_2 Stream Analytics job should belong.

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

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Get-AzureRmStreamAnalyticsJob](.\Get-AzureRmStreamAnalyticsJob.md)

[Remove-AzureRmStreamAnalyticsJob](.\Remove-AzureRmStreamAnalyticsJob.md)

[Start-AzureRmStreamAnalyticsJob](.\Start-AzureRmStreamAnalyticsJob.md)

[Stop-AzureRmStreamAnalyticsJob](.\Stop-AzureRmStreamAnalyticsJob.md)

[Stop-AzureRmStreamAnalyticsJob](.\Stop-AzureRmStreamAnalyticsJob.md)

