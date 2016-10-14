---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=397903
schema: 2.0.0
---

# Get-AzureAutomationJob

## SYNOPSIS
Gets one or more Azure Automation runbook jobs.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationJob [-Status <String>] [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-AutomationAccountName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByJobId
```
Get-AzureAutomationJob -Id <Guid> [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationJob -RunbookName <String> [-Status <String>] [-StartTime <DateTimeOffset>]
 [-EndTime <DateTimeOffset>] [-AutomationAccountName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationJob** cmdlet gets one or more runbook jobs in Microsoft Azure Automation.

## EXAMPLES

### Example 1: Get a specific runbook job
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

This command gets the job that has the specified GUID.

### Example 2: Get all jobs for a runbook
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -RunbookName "MyRunbook"
```

This command gets all jobs associated with a runbook named MyRunbook.

### Example 2: Get all running jobs
```
PS C:\>Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Status "Running"
```

This command gets all running jobs in the automation account with the name Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Azure Automation account.

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
Specifies the end time for a job as a **DateTime** object.
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
Specifies the ID of a job.

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

### -RunbookName
Specifies the name of a runbook.

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

### -Status
Specifies the status of a job.
This cmdlet gets jobs that have a status matching this parameter.
Valid values are: 

- Activating
- Blocked
- Completed
- Failed
- Queued
- Removing
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
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating, Blocked, Removing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the start time of a job as a **DateTime** object.
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

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

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

[Resume-AzureAutomationJob](.\Resume-AzureAutomationJob.md)

[Stop-AzureAutomationJob](.\Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](.\Suspend-AzureAutomationJob.md)

