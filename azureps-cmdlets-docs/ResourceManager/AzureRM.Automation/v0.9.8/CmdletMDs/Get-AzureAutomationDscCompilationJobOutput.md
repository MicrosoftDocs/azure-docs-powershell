---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationDscCompilationJob.md
schema: 2.0.0
---

# Get-AzureAutomationDscCompilationJobOutput

## SYNOPSIS
Gets the logging streams of an Automation DSC compilation job.

## SYNTAX

```
Get-AzureAutomationDscCompilationJobOutput [-Id] <Guid> [-Stream <CompilationJobStreamType>]
 [-StartTime <DateTimeOffset>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationDscCompilationJobOutput** cmdlet gets the stream records of a PowerShell Desired State Configuration (DSC) compilation job in Azure Automation.

## EXAMPLES

### Example 1: Get the logs for a DSC compilation job
```
PS C:\>$Job = Get-AzureAutomationDscCompilationJob -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
PS C:\> $Job[0] | Get-AzureAutomationDscCompilationJobOutput -Stream "Any"
```

This set of commands gets the logs of a DSC compilation job in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC compilation job.

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

### -Id
Specifies the unique ID of the DSC compilation job for which this cmdlet gets output.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: JobId

Required: True
Position: 3
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

### -ResourceGroupName
Specifies the name of the resource group that contains the DSC compilation job for which this cmdlet gets stream records.

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

### -StartTime
Specifies a start time.
This cmdlet gets stream records that the DSC compilation job outputs after this time.

```yaml
Type: DateTimeOffset
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Stream
Specifies the type of stream for the output that this cmdlet gets.
Valid values are: 

- Any 
- Warning 
- Error 
- Verbose

```yaml
Type: CompilationJobStreamType
Parameter Sets: (All)
Aliases: 
Accepted values: Any, Warning, Error, Verbose

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureAutomationDscCompilationJob](.\Get-AzureAutomationDscCompilationJob.md)

[Start-AzureAutomationDscCompilationJob](.\Start-AzureAutomationDscCompilationJob.md)

