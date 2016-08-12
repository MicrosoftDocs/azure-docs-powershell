---
external help file: RMAzure_Automation.xml
online version: 03d80a68-8443-42e0-87bc-5d0e22ac3a57
schema: 2.0.0
---

# Get-AzureRMAutomationJob
## SYNOPSIS
Gets Automation runbook jobs.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-EndTime <DateTimeOffset]>] [-StartTime <DateTimeOffset]>] [-Status]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String> -Id <Guid>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRMAutomationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-EndTime <DateTimeOffset]>] [-StartTime <DateTimeOffset]>] [-Status] -RunbookName <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationJob** cmdlet gets runbook jobs in azure_2 Automation.

## EXAMPLES

### Example 1: Get a specific runbook job
```
PS C:\>Get-AzureRmAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

This command gets the job that has the specified GUID.

### Example 2: Get all jobs for a runbook
```
PS C:\>Get-AzureRmAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbook02"
```

This command gets all jobs associated with a runbook named Runbook02.

### Example 3: Get all running jobs
```
PS C:\>Get-AzureRmAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -Status "Running"
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
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the end time for a job as a **DateTimeOffset** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.
This cmdlet gets jobs that have an end time at or before the value that this parameter specifies.

```yaml
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: JobId

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet gets jobs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -RunbookName
Specifies the name of a runbook for which this cmdlet gets jobs.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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

-- Activating
-- Completed
-- Failed
-- Queued
-- Resuming
-- Running
-- Starting
-- Stopped
-- Stopping
-- Suspended
-- Suspending

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationJobOutput](03d80a68-8443-42e0-87bc-5d0e22ac3a57)

[Resume-AzureRmAutomationJob](4b289017-5b98-45bc-87c4-86b08e1ac322)

[Stop-AzureRmAutomationJob](1b580598-1087-4a10-9bc3-747ec5d7604a)

[Suspend-AzureRmAutomationJob](cf05770c-fc18-4a31-beb9-4f8c1c39c285)

