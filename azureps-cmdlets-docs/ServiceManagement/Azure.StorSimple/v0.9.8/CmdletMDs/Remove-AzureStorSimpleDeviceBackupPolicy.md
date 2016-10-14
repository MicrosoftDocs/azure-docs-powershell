---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceBackupPolicy.md
schema: 2.0.0
---

# Remove-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Removes an existing backup policy.

## SYNTAX

### IdentifyById (Default)
```
Remove-AzureStorSimpleDeviceBackupPolicy [-DeviceName] <String> [-BackupPolicyId] <String> [-Force]
 [-WaitForComplete] [-Profile <AzureProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleDeviceBackupPolicy [-DeviceName] <String> [-BackupPolicy] <BackupPolicyDetails> [-Force]
 [-WaitForComplete] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleDeviceBackupPolicy** cmdlet removes an existing **BackupPolicy** object.
After you remove a backup policy, no further backups take place based on that policy.
This cmdlet also deletes all schedules associated with the deleted policy.

## EXAMPLES

### Example 1: Remove a backup policy
```
PS C:\>Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId "03710b4c-82c1-40ca-be5c-40289dc49642" -Force
VERBOSE: ClientRequestId: b3e4d485-eae4-4cf4-a43b-815f3abcd2dd_PS
VERBOSE: ClientRequestId: a260ee98-46aa-49e0-91ac-31d4155f4cae_PS
VERBOSE: About to create a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: 92a9c264-90df-4345-a495-92767dd266f2_PS
695be190-ac81-4cf2-b1c5-03ef6b08d005
VERBOSE: The remove task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
695be190-ac81-4cf2-b1c5-03ef6b08d005 for tracking the task's status
```

This command removes the **BackupPolicy** that has the instance ID 03710b4c-82c1-40ca-be5c-40289dc49642, so that no more backups are made based on this policy.
The command also deletes all schedules associated with this policy.
The command starts the operation that removes the **BackupPolicy** object, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.

### Example 2: Remove the first of the backup policies for a device
```
PS C:\>$Policies = Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm"
PS C:\> Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId $Policies[0].InstanceId -Force -WaitForComplete
VERBOSE: ClientRequestId: db3b49fa-cffa-446d-ba52-daa6802e00f7_PS
VERBOSE: ClientRequestId: 70e2b56f-c2df-40d0-a1e5-d7a4d7e25962_PS
VERBOSE: About to run a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: f8eb3d4d-2c57-4fc9-9f40-79d0f2ea1b6a_PS


JobId        : 820a246e-54b6-41a9-bdd5-15d5daea9b0a
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your remove operation has completed successfully.
```

The first command gets the backup policies for the device named Contoso63-AppVm, and then stores them in the $Policies variable.

The second command removes the first backup policy from Contoso63-AppVm.
The command uses standard dot syntax to identify the **InstanceId** property of the first item in $Policies.
This command specifies the *WaitForComplete* parameter, so the command completes the task, and then returns a **TaskStatusInfo** object for the task.

### Example 3: Remove a backup policy by using the pipeline
```
PS C:\>Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "TSQAVolume01_Default" | Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -Force -WaitForComplete
VERBOSE: ClientRequestId: 60080fb1-2f88-4c17-bfd7-21aa73440a9c_PS
VERBOSE: ClientRequestId: 04c91121-50d7-4796-9af6-fc6a7d6b6a0e_PS
VERBOSE: ClientRequestId: 47ceb37c-672f-42e8-bd19-1190925c46cd_PS
VERBOSE: ClientRequestId: cbc39757-f2cc-4cc5-93ea-4ec0fbfb0ca8_PS
VERBOSE: ClientRequestId: 3614d47a-51fc-4500-a5f1-5401301ca4e3_PS
VERBOSE: About to create a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: dbd7166e-1888-4b11-9af9-8d49712a8c8b_PS
702ad240-5730-4015-b051-56055bd2c2d3
VERBOSE: The remove task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
702ad240-5730-4015-b051-56055bd2c2d3 for tracking the task's status
VERBOSE: BackupPolicy with id bfe0bf8a-2d09-4690-93da-38a4f24e9f4f found!
```

This command gets a **BackupPolicyDetails** object by using **Get-AzureStorSimpleDeviceBackupPolicy**, and then passes it to the current cmdlet by using the pipeline operator.
The current cmdlet removes the backup policy named TSQAVolume01_Default.

## PARAMETERS

### -BackupPolicy
Specifies the **BackupPolicyDetails** object to delete.
To obtain a **BackupPolicyDetails** object, use the **Get-AzureStorSimpleDeviceBackupPolicy** cmdlet.

```yaml
Type: BackupPolicyDetails
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupPolicyId
Specifies the instance ID of the **BackupPolicy** object to delete.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to delete the backup policy.

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

### -Force
Indicates that this cmdlet does not prompt you for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the Windows PowerShell ‚Â® console.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BackupPolicyDetails
This cmdlet accepts a **BackupPolicyDetails** object to delete.

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackupPolicy](.\Get-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupPolicy](.\New-AzureStorSimpleDeviceBackupPolicy.md)

[Set-AzureStorSimpleDeviceBackupPolicy](.\Set-AzureStorSimpleDeviceBackupPolicy.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

