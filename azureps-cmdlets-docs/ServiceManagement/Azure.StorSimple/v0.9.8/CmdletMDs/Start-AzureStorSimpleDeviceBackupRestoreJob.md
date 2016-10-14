---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleJob.md
schema: 2.0.0
---

# Start-AzureStorSimpleDeviceBackupRestoreJob

## SYNOPSIS
Starts a job that restores a backup on a StorSimple device.

## SYNTAX

### Empty (Default)
```
Start-AzureStorSimpleDeviceBackupRestoreJob [-DeviceName] <String> [-BackupId] <String> [-WaitForComplete]
 [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

### IdentifyById
```
Start-AzureStorSimpleDeviceBackupRestoreJob [-DeviceName] <String> [-BackupId] <String> [-SnapshotId] <String>
 [-WaitForComplete] [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureStorSimpleDeviceBackupRestoreJob** cmdlet starts a job that restores a backup on a StorSimple device.
Specify a backup ID and an optional snapshot ID.

## EXAMPLES

### Example 1: Start a job to restore a backup
```
PS C:\>Start-AzureStorSimpleDeviceBackupRestoreJob -DeviceName "Contoso63-AppVm" -BackupId "b3b50534-763c-4b05-9724-5ecf62bde721" -WaitForComplete
Confirm
Are you sure you want to restore the backup with backupId b3b50534-763c-4b05-9724-5ecf62bde721? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y


Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 217d0647-c001-4f43-9833-f8155a458e95
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : e0aa2dcd2f197a8588c40a067fe0e519
```

This command starts a job that restores the backup object that has the specified ID, and its associated snapshots, on the device named Contoso63-AppVm.
The command specifies the *WaitForComplete* parameter, so the job finishes before the cmdlet returns control to the console.

### Example 2: Start a job to restore a specific snapshot
```
PS C:\>Start-AzureStorSimpleDeviceBackupRestoreJob -DeviceName "Contoso63-AppVm" -BackupId "b3b50534-763c-4b05-9724-5ecf62bde721" -SnapshotId "2d0cfad7-46bf-4266-8859-96549646e947_0000000000000000" -Force

The start job is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId 9102ed9a-078f-4648-a
721-3cffbba31336 for tracking the job status
```

This command starts a job that restores the backup snapshot that has the specified ID.
The command specifies the backup object by ID on the device named Contoso63-AppVm.
The command specifies the *Force* parameter, so it starts the job without prompting you to confirm.

## PARAMETERS

### -BackupId
Specifies the instance ID of the backup to restore.

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

### -DeviceName
Specifies the name of the StorSimple device on which the backup exists.

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
Position: 5
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

### -SnapshotId
Specifies the instance ID of the snapshot to restore.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 3
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

### None

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

[Start-AzureStorSimpleDeviceBackupJob](.\Start-AzureStorSimpleDeviceBackupJob.md)

