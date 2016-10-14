---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsOutput.md
schema: 2.0.0
---

# New-AzureStreamAnalyticsOutput

## SYNOPSIS
Creates an output within a Stream Analytics job or updates an existing output.

## SYNTAX

```
New-AzureStreamAnalyticsOutput [-JobName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStreamAnalyticsOutput** cmdlet creates an output in a Stream Analytics job or updates an existing output.
The name of the output can be specified in the .JSON file or on the command line.
If both are specified, the name on command line must be the same with the one in the file.
If you specify an output that already exists and do not specify the *Force* parameter, the cmdlet asks whether to replace the existing output.
If you specify the *Force* parameter and specify an existing output name, the output is replaced without confirmation.

## EXAMPLES

### Example 1: Create an output
```
PS C:\>New-AzureStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Output.json" -JobName "StreamingJob" -Name "Output"
```

This command creates an output named Output in the job named StreamingJob.
If an existing output named Output is already defined, the cmdlet prompts you whether to replace it.

### Example 2: Replace an existing output
```
PS C:\>New-AzureStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -File" "C:\Output.json" -JobName "StreamingJob" -Name "Output" -Force
```

This command replaces the definition for the output named Output in the job named StreamingJob.

## PARAMETERS

### -JobName
Specifies the name of the Azure Stream Analytics job that the Azure Stream Analytics output should be created under.

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
Specifies the name of the Azure Stream Analytics output to create.

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

### -File
Specifies the path to a JSON file that contains the JSON representation of the Azure Stream Analytics output to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Specifies the name of the resource group in which to create or replace an output.

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

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSOutput

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsOutput](.\Get-AzureStreamAnalyticsOutput.md)

[Remove-AzureStreamAnalyticsOutput](.\Remove-AzureStreamAnalyticsOutput.md)

[Test-AzureStreamAnalyticsOutput](.\Test-AzureStreamAnalyticsOutput.md)

