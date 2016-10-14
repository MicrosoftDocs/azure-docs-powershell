---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceBackup.md
schema: 2.0.0
---

# Start-AzureStorSimpleBackupCloneJob

## SYNOPSIS
Starts a job that clones a backup on a device.

## SYNTAX

### Empty (Default)
```
Start-AzureStorSimpleBackupCloneJob [-BackupId] <String> [-Snapshot] <Snapshot> [-CloneVolumeName] <String>
 [[-TargetAccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Start-AzureStorSimpleBackupCloneJob [-SourceDeviceName] <String> [-TargetDeviceName] <String>
 [-BackupId] <String> [-Snapshot] <Snapshot> [-CloneVolumeName] <String>
 [[-TargetAccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyById
```
Start-AzureStorSimpleBackupCloneJob [-SourceDeviceId] <String> [-TargetDeviceId] <String> [-BackupId] <String>
 [-Snapshot] <Snapshot> [-CloneVolumeName] <String>
 [[-TargetAccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureStorSimpleBackupCloneJob** cmdlet starts a job that clones an existing backup on a StorSimple device.

## EXAMPLES

### Example 1: Clone a backup to a different volume by using device names
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "ContosoDev07" -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceName "ContosoDev07 -TargetDeviceName "ContosoDev07" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

The first command gets the first backup for the device named ContosoDev07 by using the **Get-AzureStorSimpleDeviceBackup** cmdlet.
The command stores that backup in the $Backup variable.

The second command gets access control records by using the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
The command stores the result in the $Acrs variable.

The final command begins a job that clones a specified backup of a volume on a device to a different volume on the same device.
This example specifies the device by name.
The command uses the values stored in $Backup and $Acrs.
The command returns the ID of the job.

### Example 2: Clone a backup to a different volume by using device IDs
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName ContosoDev07 -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceId "be7a73a7-980c-4ba2-82d4-f6a7ee0eacbb" -TargetDeviceId "be7a73a7-980c-4ba2-82d4-f6a7ee0eacbb" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

The first command gets the first backup for the device named ContosoDev07 by using the **Get-AzureStorSimpleDeviceBackup** cmdlet.
The command stores that backup in the $Backup variable.

The second command gets access control records by using the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
The command stores the result in the $Acrs variable.

The final command begins a job that clones a specified backup of a volume on a device to a different volume on the same device.
This example specifies the device by device ID.
The command uses the values stored in $Backup and $Acrs.
The command returns the ID of the job.

### Example 3: Clone a backup to a volume on a different device by using device names
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "ContosoDev07" -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceName "ContosoDev07" -TargetDeviceName "ContosoDev12" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

The first command gets the first backup for the device named ContosoDev07 by using the **Get-AzureStorSimpleDeviceBackup** cmdlet.
The command stores that backup in the $Backup variable.

The second command gets access control records by using the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
The command stores the result in the $Acrs variable.

The final command begins a job that clones a specified backup of a volume on a device to a volume on a different device.
This example specifies the devices by name.
The command uses the values stored in $Backup and $Acrs.
The command returns the ID of the job.

### Example 4: Clone a backup to a different volume by using device names and the pipeline operator
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName ContosoDev1 -First 1
PS C:\> Get-AzureStorSimpleAccessControlRecord -ACRName acr1 | Start-AzureStorSimpleBackupCloneJob -SourceDeviceName ContosoDev1 -TargetDeviceName ContosoDev1 -BackupId $backup.InstanceId -Snapshot $backup.Snapshots[0] -CloneVolumeName "cloned_vol1" 
VERBOSE: ClientRequestId: 1183a29d-63a9-408a-9065-032c92d317ee_PS
VERBOSE: ClientRequestId: e195717c-5920-4133-bdf0-c1201ebabf6f_PS
VERBOSE: ClientRequestId: ac16644d-bfd8-4edf-b1ad-f5df4ceb4df7_PS
VERBOSE: ClientRequestId: dcdcab7f-2aaa-496d-8a18-2e7449a70227_PS
VERBOSE: ClientRequestId: 6f92e422-eda9-4087-aefb-2257a49f5beb_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 646b280c-b51c-4812-b5c5-b7ca215f1c90_PS
a747d2dc-2876-474e-aea6-6546b255427e
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId a747d2dc-2876-474e-aea6-6546b255427e for tracking the job's status
VERBOSE: Access Control Record with given name acr11 is found!
```

The first command gets the first backup for the device named ContosoDev07 by using the **Get-AzureStorSimpleDeviceBackup** cmdlet.
The command stores that backup in the $Backup variable.

The second command gets access control records by using the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
The command passes its results to the current cmdlet by using the pipeline operator.
The current cmdlet begins a job that clones a specified backup of a volume on a device, to a different volume on the same device.
This example specifies the device by name.
The command uses the value stored in $Backup.
The command takes the value of the *TargetAccessControlRecords* parameter from the pipeline.
The command returns the ID of the job.

## PARAMETERS

### -BackupId
Specifies the instance ID of the backup to clone.

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

### -CloneVolumeName
Specifies the name for the new cloned volume on the target device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
ps_force

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
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

### -Snapshot
Specifies the snapshot object that this cmdlet clones.

```yaml
Type: Snapshot
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceDeviceId
Specifies the instance ID of the source device.
This cmdlet clones the back from the source device.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDeviceName
Specifies the name of the source device.
This cmdlet clones the back from the source device.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAccessControlRecords
Specifies the access control records.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetDeviceId
Specifies the instance ID of the target device.

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

### -TargetDeviceName
Specifies the name of the device to which this cmdlet clones the backup.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Snapshot, List of AccessControlRecord
You can pipe **Snapshot** objects or a list of **AccessControlRecord** objects to this cmdlet.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackup](.\Get-AzureStorSimpleDeviceBackup.md)

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

