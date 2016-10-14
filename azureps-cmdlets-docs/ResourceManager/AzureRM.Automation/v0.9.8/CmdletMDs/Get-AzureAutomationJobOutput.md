---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationJob.md
schema: 2.0.0
---

# Get-AzureAutomationJobOutput

## SYNOPSIS
Gets the output of an Automation job.

## SYNTAX

```
Get-AzureAutomationJobOutput [-Id] <Guid> [-Stream <StreamType>] [-StartTime <DateTimeOffset>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationJobOutput** cmdlet gets the output of an Azure Automation job.

## EXAMPLES

### Example 1: Get the output of an Automation job
```
PS C:\>Get-AzureAutomationJobOutput -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01" -Stream "Any"
```

This command gets all of the output of the job that has the specified ID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet gets job output.

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

### -Id
Specifies the ID of a job for which this cmdlet gets output.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: JobId

Required: True
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

### -ResourceGroupName
The resource group name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies a start time as a **DateTimeOffset** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.
The cmdlet retrieves output created after this time.

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
Specifies the type of output.
Valid values are: 

- Any
- Debug
- Error
- Output
- Progress
- Verbose
- Warning

```yaml
Type: StreamType
Parameter Sets: (All)
Aliases: 
Accepted values: Any, Progress, Output, Warning, Error, Debug, Verbose

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

[Get-AzureAutomationJob](.\Get-AzureAutomationJob.md)

[Resume-AzureAutomationJob](.\Resume-AzureAutomationJob.md)

[Stop-AzureAutomationJob](.\Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](.\Suspend-AzureAutomationJob.md)

