---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceBackupPolicy.md
schema: 2.0.0
---

# New-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Creates a backup policy.

## SYNTAX

```
New-AzureStorSimpleDeviceBackupPolicy [-DeviceName] <String> [-BackupPolicyName] <String>
 [-BackupSchedulesToAdd] <PSObject[]> [-VolumeIdsToAdd] <PSObject[]> [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleDeviceBackupPolicy** cmdlet creates a backup policy.
A backup policy contains one or more backup schedules that can run on one or more volumes.
To create a backup schedule, use the **New-AzureStorSimpleDeviceBackupScheduleAddConfig** cmdlet.

## EXAMPLES

### Example 1: Create a backup policy
```
PS C:\>$Schedule01 = New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType LocalSnapshot -RecurrenceType Daily -RecurrenceValue 10 -RetentionCount 5 -Enabled $True
PS C:\> $Schedule02 = New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType CloudSnapshot -RecurrenceType Hourly -RecurrenceValue 1 -RetentionCount 5 -Enabled $True
PS C:\> $ScheduleArray = @()
PS C:\> $ScheduleArray += $Schedule01
PS C:\> $ScheduleArray += $Schedule02
PS C:\> $DeviceContainer = Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm"
PS C:\> $Volume = $(Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeContainer $DeviceContainer[0])
PS C:\> $VolumeArray = @()
PS C:\> $VolumeArray += $Volume[0].InstanceId
PS C:\> New-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "GeneralPolicy07" -BackupSchedulesToAdd $ScheduleArray -VolumeIdsToAdd $VolumeArray
VERBOSE: ClientRequestId: e9d6771e-c323-47b9-b424-cb98f8ed0273_PS
VERBOSE: ClientRequestId: db0e7c86-d0d2-4a5a-b1cb-182494cba027_PS
VERBOSE: ClientRequestId: 77708dfd-a386-4999-b7ed-5d53e288ae83_PS


JobId        : d4ce5340-d5d1-4471-9cc8-013193f021b3
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your add operation has completed successfully. 
VERBOSE: ClientRequestId: bbf7e9b9-b493-40b3-8348-f15bcfc4da8a_PS
BackupSchedules          : {36d21096-bbd1-47b7-91b5-40ad1792d992, 505fc91f-deb5-4dca-bfcb-98c20b75ebcc}
Volumes                  : {volume03}
BackupPolicyCreationType : BySaaS
LastBackup               : 01-01-2010 05:30:00
NextBackup               : 16-12-2014 01:13:43
SchedulesCount           : 2
SSMHostName              : 
VolumesCount             : 1
InstanceId               : 8799c2f0-8850-4e91-aa23-ee18c67da8bd
Name                     : GeneralPolicy07
OperationInProgress      : None
```

The first command creates a backup schedule configuration object by using the **New-AzureStorSimpleDeviceBackupScheduleAddConfig** cmdlet, and then stores that object in the $Schedule01 variable.

The second command creates another backup configuration object by using **New-AzureStorSimpleDeviceBackupScheduleAddConfig**, and then stores that object in the $Schedule02 variable.

The third command creates an empty array variable, named $ScheduleArray.
The next two commands add the objects created in the first two commands to $ScheduleArray.

The sixth command gets a volume container for the device named Contoso63-AppVm by using the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet, and then stores that container object in the $DeviceContainer variable.

The seventh command gets a volume for the volume container stored in the first member of $DeviceContainer by using the **Get-AzureStorSimpleDeviceVolume** cmdlet, and then stores that volume in the $Volume variable.

The eighth command creates an empty array variable, named $VolumeArray.
The next command adds a volume ID to $VolumeArray.
This value identifies the volume, stored in $Volume, on which the backup policy runs.
You can add additional volume IDs to $VolumeArray.

The final command creates the backup policy named GeneralPolicy07 for the device named Contoso63-AppVm.
The command specifies the schedule configuration objects stored in $ScheduleArray.
The command specifies the volume or volumes to which to apply the policy in $VolumeArray.
You can verify the backup policy by using the **Get-AzureStorSimpleDeviceBackupPolicy** cmdlet.

## PARAMETERS

### -BackupPolicyName
Specifies the name of the backup policy.

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

### -BackupSchedulesToAdd
Specifies an array of **BackupScheduleBase** objects to add to the policy.
Each object represents a schedule.
A backup policy contains one or more schedules.
To obtain a **BackupScheduleBase** object, use the **New-AzureStorSimpleDeviceBackupScheduleAddConfig** cmdlet.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to create the backup policy.

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

### -VolumeIdsToAdd
Specifies an array of the IDs of volumes to add to the backup policy.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### BackupPolicy
This cmdlet returns a **BackupPolicy** object that contains the new schedules and volumes.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackupPolicy](.\Get-AzureStorSimpleDeviceBackupPolicy.md)

[Get-AzureStorSimpleDeviceVolume](.\Get-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

[Remove-AzureStorSimpleDeviceBackupPolicy](.\Remove-AzureStorSimpleDeviceBackupPolicy.md)

[Set-AzureStorSimpleDeviceBackupPolicy](.\Set-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupScheduleAddConfig](.\New-AzureStorSimpleDeviceBackupScheduleAddConfig.md)

