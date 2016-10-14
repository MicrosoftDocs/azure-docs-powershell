---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceBackup.md
schema: 2.0.0
---

# Remove-AzureStorSimpleDeviceBackup

## SYNOPSIS
Deletes a backup object.

## SYNTAX

### IdentifyById (Default)
```
Remove-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-BackupId] <String> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-Backup] <Backup> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleDeviceBackup** cmdlet deletes a single backup object.
If you attempt to delete a backup that has already been deleted, this cmdlet returns an error.

## EXAMPLES

### Example 1: Remove a backup for a device
```
PS C:\>Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupId "dcb5c991-0485-400f-8d0a-03a1341ee989" -Force
The remove job is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId 6c73aff2-f5a1-4b5e-
9a4e-857e128dc216 for tracking the job status
```

This command removes the backup that has the specified ID for the device named Contoso63-AppVm.
The command starts the operation that removes the **Backup** object, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.

### Example 2: Remove the first backup for a device by using its ID
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm"
PS C:\> Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupId $Backup[0].InstanceId -WaitForComplete
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 53a656c3-c082-4e1f-afb7-bff3db45c791
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : f4411f38d07f68b88095682dbeedd9e9
```

The first command gets the backups for the device named Contoso63-AppVm, and then stores them in the $Backup variable.

The second command deletes a backup from the device named Contoso63-AppVm.
The command uses standard dot notation to refer to the **InstanceId** property of the first element of the $Backup array.
This command specifies the *WaitForComplete* parameter, and, therefore, the command waits until the operation is complete, and then returns a **TaskStatusInfo** object.

### Example 3: Remove the first backup for a device by using the pipeline
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso-AppVm" -WaitForComplete
PS C:\> $Backup[0] | Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso-AppVm" -Force -WaitForComplete
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 48059fd8-e355-4b91-9385-630d24f31df6
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : e1753f3bf68e6e44ab719436b5111e41
```

The first command gets the backups for the device named Contoso63-AppVm, and then stores them in the $Backup variable.

The second command passes the first object stored in the $Backup array to the current cmdlet.
That cmdlet deletes that backup from the device named Contoso63-AppVm.
This command specifies the *WaitForComplete* parameter, and, therefore, the command waits until the operation is complete, and then returns a **TaskStatusInfo** object.

## PARAMETERS

### -Backup
Specifies the **Backup** object to delete.
To obtain a **Backup** object, use the **Get-AzureStorSimpleDeviceBackup** cmdlet.

```yaml
Type: Backup
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupId
Specifies the instance ID of a backup to delete.

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
Specifies the name of the StorSimple device on which to delete a backup.

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
Specifies an azure_2 profile.

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

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the wps_1 console.

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

### Backup

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackup](.\Get-AzureStorSimpleDeviceBackup.md)

