---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceBackupPolicy.md
schema: 2.0.0
---

# Set-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Updates an existing backup policy.

## SYNTAX

```
Set-AzureStorSimpleDeviceBackupPolicy [-DeviceName] <String> [-BackupPolicyId] <String>
 [-BackupPolicyName] <String> [[-BackupSchedulesToAdd] <PSObject[]>] [[-BackupSchedulesToUpdate] <PSObject[]>]
 [[-BackupScheduleIdsToDelete] <PSObject[]>] [[-VolumeIdsToUpdate] <PSObject[]>] [-WaitForComplete]
 [[-NewName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleDeviceBackupPolicy** cmdlet updates an existing backup policy.
You can rename the policy, add, update or delete schedules, and update the volumes associated with the policy.

## EXAMPLES

### Example 1: Change the name of a backup policy
```
PS C:\>Set-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId "e6d9f1b3-a250-4d57-966a-039c8eaef9e9" -BackupPolicyName "UpdatedGeneralPolicy07" -WaitForComplete
VERBOSE: ClientRequestId: f4465b46-26cc-40ff-88da-7a28df88c35c_PS
VERBOSE: ClientRequestId: 5e33a35c-e089-47c1-b760-474635b1ead8_PS
VERBOSE: About to run a task to update your backuppolicy! 
VERBOSE: ClientRequestId: e379ebdb-667f-45a9-aafa-a6cd61e5f6f6_PS


JobId        : 9d621bfd-3faa-4d1c-b28b-45c5f4a96975
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your update operation has completed successfully. 
VERBOSE: ClientRequestId: 4fe965ea-4e12-4869-9d67-e42a24b6c5d8_PS
BackupSchedules          : {58e9cd7c-4c6a-4e33-9109-5ec0b8fcb2cc, b10e1bf4-ef0a-4ad3-8fde-eecfc9971dd2}
Volumes                  : {testvolume03}
BackupPolicyCreationType : BySaaS
LastBackup               : 12/16/2014 2:13:28 PM
NextBackup               : 12/16/2014 3:13:43 PM
SchedulesCount           : 2
SSMHostName              : 
VolumesCount             : 1
InstanceId               : e6d9f1b3-a250-4d57-966a-039c8eaef9e9
Name                     : UpdatedGeneralPolicy07
OperationInProgress      : None
```

This command changes the name of the backup policy that has the specified ID to UpdatedGeneralPolicy07.
This command specifies the *WaitForComplete* parameter, so the command completes the task, and then returns a **TaskStatusInfo** object for the task.

### Example 2: Update the schedule for a backup policy
```
PS C:\>$UpdateConfig = New-AzureStorSimpleDeviceBackupScheduleUpdateConfig -Id "3a6c6247-6b4d-42e2-aa87-16f4f21476ea" -BackupType CloudSnapshot -RecurrenceType Daily -RecurrenceValue 3 -RetentionCount 2 -Enabled $True
PS C:\> $UpdateArray = @()
PS C:\> $UpdateArray += $UpdateConfig
PS C:\> Set-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId "712605f6-eb03-4db8-8f79-e0ce64b2cce1" -BackupSchedulesToUpdate $UpdateArray
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 7b265417-a5f1-45ad-8fbc-33bad4f63ec9
JobSteps   : {Microsoft.WindowsAzure.Management.StorSimple.Models.JobStep, 
             Microsoft.WindowsAzure.Management.StorSimple.Models.JobStep, 
             Microsoft.WindowsAzure.Management.StorSimple.Models.JobStep, 
             Microsoft.WindowsAzure.Management.StorSimple.Models.JobStep...} 
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : d2e10d44e699b371a84db44d19daf1c3
```

The first command creates an update configuration object by using the **New-AzureStorSimpleDeviceBackupScheduleUpdateConfig** cmdlet, and then stores it in the $UpdateConfig variable.

The second command creates a new array variable, named $UpdateArray.
The next command adds the update stored in $UpdateConfig to that array.
You can add more than one update to the array.

The final command updates the backup policy that has the specified ID on the device named Contoso63-AppVm.
The policy now has the updated schedule stored in $UpdateArray.

## PARAMETERS

### -BackupPolicyId
Specifies the instance ID of the **BackupPolicy** object to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupPolicyName
Specifies a new name for the backup policy.

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

### -BackupScheduleIdsToDelete
Specifies an array of instance IDs of **BackupSchedule** objects to delete.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupSchedulesToAdd
Specifies an array of **BackupScheduleBase** objects to add to the policy.
To obtain a **BackupScheduleBase** object, use the **New-AzureStorSimpleDeviceBackupScheduleAddConfig** cmdlet.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupSchedulesToUpdate
Specifies an array of **BackupScheduleUpdateRequest** objects to update.
To obtain a **BackupScheduleUpdateRequest** object, use the **New-AzureStorSimpleDeviceBackupScheduleUpdateConfig** cmdlet.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device for which to update the backup policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a name for the device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### -VolumeIdsToUpdate
Specifies an array of IDs of volumes for which to update backup policies.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the Windows PowerShell ‚Â® console.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackupPolicy](.\Get-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupPolicy](.\New-AzureStorSimpleDeviceBackupPolicy.md)

[Remove-AzureStorSimpleDeviceBackupPolicy](.\Remove-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupScheduleUpdateConfig](.\New-AzureStorSimpleDeviceBackupScheduleUpdateConfig.md)

