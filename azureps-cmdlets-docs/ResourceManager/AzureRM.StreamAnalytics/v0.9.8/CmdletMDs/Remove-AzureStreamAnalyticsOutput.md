---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: .\Get-AzureStreamAnalyticsOutput.md
schema: 2.0.0
---

# Remove-AzureStreamAnalyticsOutput

## SYNOPSIS
Asynchronously removes an output from a Stream Analytics job in Microsoft Azure.

## SYNTAX

```
Remove-AzureStreamAnalyticsOutput [-JobName] <String> [-Name] <String> [-Force] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStreamAnalyticsOutput** cmdlet asynchronously removes a specified output from an Azure Stream Analytics job in Microsoft Azure.
If you specify the *Force* parameter the output is deleted without confirmation.

## EXAMPLES

### Example 1: Remove an output for a job
```
PS C:\>Remove-AzureStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -Name "Output" -Force
```

This command removes the output named Output from the job named StreamingJob, and does not prompt you for confirmation.

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
Specifies the name of the Azure Stream Analytics output to remove.

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

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureStreamAnalyticsOutput](.\Get-AzureStreamAnalyticsOutput.md)

[New-AzureStreamAnalyticsOutput](.\New-AzureStreamAnalyticsOutput.md)

[Test-AzureStreamAnalyticsOutput](.\Test-AzureStreamAnalyticsOutput.md)

