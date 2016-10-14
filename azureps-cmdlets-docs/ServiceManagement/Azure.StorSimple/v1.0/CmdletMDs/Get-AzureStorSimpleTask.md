---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: d6e31a21-f027-4075-955a-d6e0344a6805
schema: 2.0.0
---

# Get-AzureStorSimpleTask

## SYNOPSIS
Gets status of a task on a StorSimple device.

## SYNTAX

```
Get-AzureStorSimpleTask [-InstanceId] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleTask** cmdlet retrieves the status of a task that runs asynchronously on an azure_2 StorSimple device.

While you manage a StorSimple device, most create, read, update, and delete actions can run asynchronously.
wps_2 returns a **TaskId**.
Use the ID to get the current status of the task.

## EXAMPLES

### Example 1: Get the status of a task
```
PS C:\>Get-AzureStorSimpleTask -TaskId "53816d8d-a8b5-4c1d-a177-e59007608d6d"
VERBOSE: ClientRequestId: d9c1e8a7-994f-4698-8b42-064600b45cad_PS
VERBOSE: ClientRequestId: aae17c82-6fd3-435e-a965-1c66b3c955fe_PS


AsyncTaskAggregatedResult : Succeeded
Error                     : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
Result                    : Succeeded
Status                    : Completed
TaskId                    : 53816d8d-a8b5-4c1d-a177-e59007608d6d
TaskSteps                 : {}
StatusCode                : OK
RequestId                 : e9174990825750bba69383748f23019c
```

This command gets the status of the task that has the specified ID.
The results show that the task has a status of completed and a result of successful.

## PARAMETERS

### -InstanceId
Specifies the ID of the task for which this cmdlet tracks status.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TaskId

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

```yaml
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

### None

## OUTPUTS

### JobStatusInfo
This cmdlet returns a **TaskStatusInfo** object which contains the following fields: 

- **Error**.
**ErrorDetails**, which contains **Code** and **Message**.
- **TaskId**.
**String**.
The ID of the task for which status is returned.
- **TaskSteps**.
**IList\<TaskStep\>**.
Each **TaskStep** object contains **Detail**, **ErrorCode**, **Message**, **Result**, and **Status**.
- **Result**.
**TaskResult**, which contains the overall result of the task.
Valid values are: Failed, Succeeded, PartialSuccess, Cancelled, and Invalid.
- **Status**.
**TaskStatus**, which contains the overall running status of the task.
Valid values are: Inprogress, Invalid, and Completed.
- **TaskResult**.
**TaskResult**, a value computed based on **Result** and **Status**.
Valid values are: Failed, Succeeded, InProgress, PartialSuccess, Cancelled, and Invalid.

## NOTES

## RELATED LINKS

