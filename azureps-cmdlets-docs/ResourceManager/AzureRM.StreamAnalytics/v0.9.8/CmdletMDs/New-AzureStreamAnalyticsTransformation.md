---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsTransformation.md
schema: 2.0.0
---

# New-AzureStreamAnalyticsTransformation

## SYNOPSIS
Creates a transformation in a Stream Analytics job or updates the existing transformation.

## SYNTAX

```
New-AzureStreamAnalyticsTransformation [-JobName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStreamAnalyticsTransformation** cmdlet creates a transformation in a Stream Analytics job or updates the existing transformation.
The name of the transformation can be specified in the .JSON file or on the command line.
If both are specified, the name on command line must be the same with the one in the file.
If you specify a transformation that already exists and do not specify the *Force* parameter, the cmdlet will ask whether or not to replace the existing transformation.
If you specify the *Force* parameter and specify an existing transformation name, the transformation is replaced without confirmation.

## EXAMPLES

### Example 1: Create a transformation
```
PS C:\>New-AzureStreamAnalyticsTransformation -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Transformation.json" -JobName "StreamingJob" -Name "StreamingJobTransform"
```

This command creates a transformation named StreamingJobTransform for the job named StreamingJob.
If there is an existing transformation named StreamingJobTransform, the cmdlet prompts you whether to replace it.

### Example 2: Replace an existing transformation
```
PS C:\>New-AzureStreamAnalyticsTransformation -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Transformation.json" -JobName "StreamingJob" -Name "StreamingJobTransform" -Force
```

This command replaces the definition of the transformation named StreamingJobTransform for the job named StreamingJob.

## PARAMETERS

### -JobName
Specifies the name of the job for which to create or replace the transformation.

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
Specifies the name of the Azure Stream Analytics transformation to create.

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
Specifies the path to a JSON file that contains the JSON representation of the Azure Stream Analytics transformation to create.

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
Indicates that this cmdlet replaces the specified Azure Stream Analytics transformation if it already exists without asking for confirmation.

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
Specifies the name of the resource group that the Azure Stream Analytics transformation should be created under.

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

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSTransformation

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsTransformation](.\Get-AzureStreamAnalyticsTransformation.md)

