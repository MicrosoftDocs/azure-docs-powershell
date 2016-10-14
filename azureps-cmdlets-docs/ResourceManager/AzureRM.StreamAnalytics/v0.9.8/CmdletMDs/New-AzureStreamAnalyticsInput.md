---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsInput.md
schema: 2.0.0
---

# New-AzureStreamAnalyticsInput

## SYNOPSIS
Creates a new input within a Stream Analytics job or updates an existing specified input.

## SYNTAX

```
New-AzureStreamAnalyticsInput [-JobName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStreamAnalyticsInput** cmdlet creates a new input within a Stream Analytics job or updates an existing specified input.
The name of the input can be specified in the .JSON file or on the command line.
If both are specified, the name on command line must be the same with the one in the file.
If you specify an input that already exists and do not specify the *Force* parameter, the cmdlet prompts whether to replace the existing input.
If you specify the *Force* parameter and specify an existing input name, the input is replaced without confirmation.

## EXAMPLES

### Example 1: Create an input and use a .JSON file to specify its name
```
PS C:\>New-AzureStreamAnalyticsInput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -File "C:\Input.json"
```

This command creates an input from the definition file Input.json.
If an existing input with the same name is specified in Input.json, the cmdlet prompts you whether to replace it.

### Example 2: Create an input and use the command line to specify its name
```
PS C:\>New-AzureStreamAnalyticsInput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -File "C:\Input.json" -Name "EntryStream"
```

This command creates an input named EntryStream for the job named StreamingJob.
If an existing input has the same name, the cmdlet prompts you whether to replace it.

### Example 3: Replace an existing input
```
PS C:\>New-AzureStreamAnalyticsInput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -File "C:\Input.json" -Name "EntryStream" -Force
```

This command replaces the definition of the existing input named EntryStream with the definition in the file Input.json.

## PARAMETERS

### -JobName
Specifies the name of the Azure Stream Analytics input to create.

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
Specifies the name of the Azure Stream Analytics input to create.

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
Specifies the path to a JSON file that contains the JSON representation of the Azure Stream Analytics input to create.

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
Indicates that the cmdlet will replace the specified Azure Stream Analytics input if it already exists without asking for confirmation.

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
Specifies the name of the resource group that the Azure Streaming input should be created under.

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

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSInput

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsInput](.\Get-AzureStreamAnalyticsInput.md)

[Remove-AzureStreamAnalyticsInput](.\Remove-AzureStreamAnalyticsInput.md)

[Test-AzureStreamAnalyticsInput](.\Test-AzureStreamAnalyticsInput.md)

