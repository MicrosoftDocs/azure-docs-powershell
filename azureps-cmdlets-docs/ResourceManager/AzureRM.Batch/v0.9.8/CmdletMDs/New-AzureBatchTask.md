---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# New-AzureBatchTask

## SYNOPSIS
Creates a new Batch task under the specified job.

## SYNTAX

### Id
```
New-AzureBatchTask -JobId <String> -Id <String> [-DisplayName <String>] -CommandLine <String>
 [-ResourceFiles <IDictionary>] [-EnvironmentSettings <IDictionary>] [-RunElevated]
 [-AffinityInformation <PSAffinityInformation>] [-Constraints <PSTaskConstraints>]
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ParentObject
```
New-AzureBatchTask [-Job <PSCloudJob>] -Id <String> [-DisplayName <String>] -CommandLine <String>
 [-ResourceFiles <IDictionary>] [-EnvironmentSettings <IDictionary>] [-RunElevated]
 [-AffinityInformation <PSAffinityInformation>] [-Constraints <PSTaskConstraints>]
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureBatchTask** cmdlet creates a new Azure Batch task under the job specified by the *JobId* parameter or the *Job* parameter.

## EXAMPLES

### Example 1: Create a new Batch task
```
PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "MyTask" -CommandLine "cmd /c dir /s" -BatchContext $Context
```

This command creates a new task with ID MyTask under job Job-000001.
The task will run the command-line "cmd /c dir /s".

### Example 2: Create a new Batch task
```
PS C:\>Get-AzureBatchJob -Id "Job-000001" -BatchContext $Context | New-AzureBatchTask -Id "MyTask2" -CommandLine "cmd /c echo hello > newFile.txt" -RunElevated -BatchContext $Context
```

This command creates a new task with ID MyTask2 under job Job-000001.
The task will run the command-line "cmd /c echo hello \> newFile.txt" with elevated permissions.

## PARAMETERS

### -AffinityInformation
Specifies a locality hint that can be used by the Batch service to select a node on which to start the task.

```yaml
Type: PSAffinityInformation
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -CommandLine
Specifies the command-line command for the task.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Constraints
Specifies the run constraints for the task.

```yaml
Type: PSTaskConstraints
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the task.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentSettings
Specifies the environment settings to add to the new task.
For each key/value pair, set the key to the environment setting name, and the value to the environment setting.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the task to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the **PSCloudJob** object representing the job to create the task under.
Use the Get-AzureBatchJob cmdlet to get a **PSCloudJob** object.

```yaml
Type: PSCloudJob
Parameter Sets: ParentObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Specifies the ID of the job to create the task under.

```yaml
Type: String
Parameter Sets: Id
Aliases: 

Required: True
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

### -ResourceFiles
Specifies resource files required by the task.
For each key/value pair, set the key to the resource file path, and the value to the resource file blob source.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunElevated
Indicates that the task process runs elevated as Administrator.
Otherwise, the process runs without elevation.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureBatchAccountKeys](.\Get-AzureBatchAccountKeys.md)

[Get-AzureBatchJob](.\Get-AzureBatchJob.md)

[Get-AzureBatchTask](.\Get-AzureBatchTask.md)

[Remove-AzureBatchTask](.\Remove-AzureBatchTask.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

