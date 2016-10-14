---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# Get-AzureBatchTask

## SYNOPSIS
Gets the Batch tasks for the specified job.

## SYNTAX

### ODataFilter (Default)
```
Get-AzureBatchTask [-JobId] <String> [-Filter <String>] [-MaxCount <Int32>] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Id
```
Get-AzureBatchTask [-JobId] <String> [[-Id] <String>] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ParentObject
```
Get-AzureBatchTask [[-Job] <PSCloudJob>] [-Filter <String>] [-MaxCount <Int32>]
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureBatchTask** cmdlet gets the Azure Batch tasks for the job specified by either the *JobId* parameter or the *Job* parameter.
You can use the *Id* parameter to get a single task, or you can use the *Filter* parameter to get the tasks that match an **OData** filter.

## EXAMPLES

### Example 1: Get a task by ID
```
PS C:\>Get-AzureBatchTask -JobId "Job01" -Id "MyTask" -BatchContext $Context
AffinityInformation         : 
CommandLine                 : cmd /c dir /s
ComputeNodeInformation      : Microsoft.Azure.Commands.Batch.Models.PSComputeNodeInformation
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSTaskConstraints
CreationTime                : 7/25/2015 11:24:52 PM
DisplayName                 : 
EnvironmentSettings         : 
ETag                        : 0x8D295483E08BD9D
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSTaskExecutionInformation
Id                          : MyTask
LastModified                : 7/25/2015 11:24:52 PM
PreviousState               : Running
PreviousStateTransitionTime : 7/25/2015 11:24:59 PM
ResourceFiles               : 
RunElevated                 : False
State                       : Completed
StateTransitionTime         : 7/25/2015 11:24:59 PM
Statistics                  : 
Url                         : https://cmdletexample.westus.batch.azure.com/jobs/Job01/tasks/MyTask
```

This command gets the task with ID MyTask under job Job01.

### Example 2: Get all completed tasks from a specified job
```
PS C:\>Get-AzureBatchTask -JobId "Job02" -Filter "state eq 'completed'" -BatchContext $Context
AffinityInformation         : 
CommandLine                 : cmd /c dir /s
ComputeNodeInformation      : Microsoft.Azure.Commands.Batch.Models.PSComputeNodeInformation
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSTaskConstraints
CreationTime                : 3/24/2015 10:21:51 PM
EnvironmentSettings         : 
ETag                        : 0x8D295483E08BD9D
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSTaskExecutionInformation
Id                          : MyTask
LastModified                : 3/24/2015 10:21:51 PM
PreviousState               : Running
PreviousStateTransitionTime : 3/24/2015 10:22:00 PM
ResourceFiles               : 
RunElevated                 : False
State                       : Completed
StateTransitionTime         : 3/24/2015 10:22:00 PM
Statistics                  : 
Url                         : https://cmdletexample.westus.batch.azure.com/jobs/Job02/tasks/MyTask

AffinityInformation         : 
CommandLine                 : cmd /c echo hello > newFile.txt
ComputeNodeInformation      : Microsoft.Azure.Commands.Batch.Models.PSComputeNodeInformation
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSTaskConstraints
CreationTime                : 3/24/2015 10:21:51 PM
EnvironmentSettings         : 
ETag                        : 0x8D295483E08BD9D
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSTaskExecutionInformation
Id                          : MyTask2
LastModified                : 3/24/2015 10:23:35 PM
PreviousState               : Running
PreviousStateTransitionTime : 3/24/2015 10:23:37 PM
ResourceFiles               : 
RunElevated                 : True
State                       : Completed
StateTransitionTime         : 3/24/2015 10:23:37 PM
Statistics                  : 
Url                         : https://cmdletexample.westus.batch.azure.com/jobs/Job02/tasks/MyTask2
```

This command gets the completed tasks from the job with ID Job02.

## PARAMETERS

### -BatchContext
Specifies the **BatchAccountContext** instance that this cmdlet uses to interact with the Batch service.
To obtain a **BatchAccountContext** object that contains access keys for your subscription, use the Get-AzureBatchAccountKeys cmdlet.

```yaml
Type: BatchAccountContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Filter
Specifies the **OData** filter clause to use when querying for tasks.
If you do not specify a filter, then all tasks under the job specified with either the *JobId* parameter or the *Job* parameter will be returned.

```yaml
Type: String
Parameter Sets: ODataFilter, ParentObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the task to retrieve.
You cannot specify wildcard characters.

```yaml
Type: String
Parameter Sets: Id
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the **PSCloudJob** object representing the job which contains the tasks.
Use the Get-AzureBatchJob cmdlet to get a **PSCloudJob** object.

```yaml
Type: PSCloudJob
Parameter Sets: ParentObject
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Specifies the ID of the job which contains the tasks.

```yaml
Type: String
Parameter Sets: ODataFilter, Id
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxCount
Specifies the maximum number of tasks to return.
If you specify a value of zero (0) or less, the cmdlet does not use an upper limit.
The default value is 1000.

```yaml
Type: Int32
Parameter Sets: ODataFilter, ParentObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCloudTask

## NOTES

## RELATED LINKS

[Get-AzureBatchAccountKeys](.\Get-AzureBatchAccountKeys.md)

[Get-AzureBatchJob](.\Get-AzureBatchJob.md)

[New-AzureBatchTask](.\New-AzureBatchTask.md)

[Remove-AzureBatchTask](.\Remove-AzureBatchTask.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

