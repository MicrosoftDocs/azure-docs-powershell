---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationJobOutput.md
schema: 2.0.0
---

# Get-AzureAutomationJob

## SYNOPSIS
Gets Automation runbook jobs.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationJob [-Status <String>] [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByJobId
```
Get-AzureAutomationJob -Id <Guid> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationJob -RunbookName <String> [-Status <String>] [-StartTime <DateTimeOffset>]
 [-EndTime <DateTimeOffset>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationJob** cmdlet gets runbook jobs in Azure Automation.

## EXAMPLES

### Example 1: Get a specific runbook job
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

This command gets the job that has the specified GUID.

### Example 2: Get all jobs for a runbook
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "MyRunbook"
```

This command gets all jobs associated with a runbook named MyRunbook.

### Example 3: Get all running jobs
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -Status "Running"
```

This command gets all running jobs in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet gets jobs.

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

### -EndTime
Specifies the end time for a job as a **DateTimeOffset** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.
This cmdlet gets jobs that have an end time at or before the value that this parameter specifies.

```yaml
Type: DateTimeOffset
Parameter Sets: ByAll, ByRunbookName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of a job that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: ByJobId
Aliases: JobId

Required: True
Position: Named
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

### -RunbookName
Specifies the name of a runbook for which this cmdlet gets jobs.

```yaml
Type: String
Parameter Sets: ByRunbookName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the start time of a job as a **DateTimeOffset** object.
This cmdlet gets jobs that have a start time at or after the value that this parameter specifies.

```yaml
Type: DateTimeOffset
Parameter Sets: ByAll, ByRunbookName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies the status of a job.
This cmdlet gets jobs that have a status matching this parameter.
Valid values are: 

- Activating
- Completed
- Failed
- Queued
- Resuming
- Running
- Starting
- Stopped
- Stopping
- Suspended
- Suspending

```yaml
Type: String
Parameter Sets: ByAll, ByRunbookName
Aliases: 
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating

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

### Microsoft.Azure.Commands.Automation.Model.Job

## NOTES

## RELATED LINKS

[Get-AzureAutomationJobOutput](.\Get-AzureAutomationJobOutput.md)

[Resume-AzureAutomationJob](.\Resume-AzureAutomationJob.md)

[Stop-AzureAutomationJob](.\Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](.\Suspend-AzureAutomationJob.md)

