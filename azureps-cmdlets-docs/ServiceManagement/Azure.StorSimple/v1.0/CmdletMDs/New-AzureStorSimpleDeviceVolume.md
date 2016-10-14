---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceVolume.md
schema: 2.0.0
---

# New-AzureStorSimpleDeviceVolume

## SYNOPSIS
Creates a volume in a specified volume container.

## SYNTAX

```
New-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-VolumeContainer] <DataContainer>
 [-VolumeName] <String> [-VolumeSizeInBytes] <Int64>
 [-AccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>
 [-VolumeAppType] <AppType> [-Online] <Boolean> [-EnableDefaultBackup] <Boolean> [-EnableMonitoring] <Boolean>
 [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleDeviceVolume** cmdlet creates a volume in a specified volume container.
This cmdlet associates each volume with one or more access control records.
To obtain **AccessControlRecord** objects, use the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
Specify a name, size, and AppType for the volume.
Also, specify whether to create the volume online, whether to enable default backup, and whether to enable monitoring.

## EXAMPLES

### Example 1: Create a volume
```
PS C:\>$AcrList = Get-AzureStorSimpleAccessControlRecord
PS C:\> Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "VolumeContainer07" | New-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" -Size 2000000000 -AccessControlRecords $AcrList -VolumeAppType PrimaryVolume -Online $True -EnableDefaultBackup $False -EnableMonitoring $False

VERBOSE: ClientRequestId: a29d1a84-1f81-4f20-9130-7adfe45e41fb_PS
VERBOSE: ClientRequestId: 8fa63df1-3f81-4029-a536-b536a70068ad_PS
VERBOSE: ClientRequestId: 964c5744-8bb1-4f70-beda-95ca4c7f3eb6_PS
VERBOSE: ClientRequestId: f09fff3a-54fa-4a0e-93db-b079260ed2dd_PS
VERBOSE: ClientRequestId: 59aa29e3-8044-411a-adae-b64a2681ffed_PS
VERBOSE: ClientRequestId: 0ffd0297-19be-40fe-a64e-6a2947d831b4_PS
c3b1ad53-7a51-49d7-ae83-94ff1ff3ab90
VERBOSE: The create task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
c3b1ad53-7a51-49d7-ae83-94ff1ff3ab90 for tracking the task's status
VERBOSE: Volume container with name: VolumeContainer07 is found.
```

The first command gets the access control records in the StorSimple Manager service configuration by using the **Get-AzureStorSimpleAccessControlRecord** cmdlet, and then stores them in the $AcrList variable.

The second command gets the volume container named VolumeContainer07 for the device named Contoso63-AppVm by using the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.
The command passes that container to the current cmdlet by using the pipeline operator.
This cmdlet creates the volume.
The command specifies the name for the volume, the size, and the access control records stored in $AcrList.
This command starts the job, and then returns a **TaskResponse** object.
To see the status of the job, use the **Get-AzureStorSimpleTask** cmdlet.

### Example 2: Create a volume without Access Controlaccess control recordsaccess control
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "VolumeContainer01" | New-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume22" -Size 2000000000 -AccessControlRecords @() -VolumeAppType PrimaryVolume -Online $True -EnableDefaultBackup $False -EnableMonitoring $False -WaitForComplete
VERBOSE: ClientRequestId: 3f359790-7e1f-48e7-acf8-ecabba850966_PS
VERBOSE: ClientRequestId: 2723ebcf-cd72-47bb-99b5-0c099d45641b_PS
VERBOSE: ClientRequestId: e605091f-dd63-42a7-bda2-24753cbc1f9a_PS
VERBOSE: ClientRequestId: b3fd08c3-67c5-4309-9591-15d92c360469_PS
VERBOSE: ClientRequestId: 15a024a3-b0c9-4f83-9c34-0ed8b95d024b_PS
VERBOSE: ClientRequestId: c13f92f9-aea1-40dd-af80-3affe273adbe_PS


TaskId       : ceef657e-390e-4f7a-aab7-669a29c29e7f
TaskResult   : Succeeded
TaskStatus   : Completed
ErrorCode    : 
ErrorMessage : 
TaskSteps    : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The task created for your create operation has completed successfully. 
VERBOSE: ClientRequestId: 1d79febf-f752-4255-af2d-230d40773bc6_PS
AccessType             : NoAccess
AcrIdList              : {}
AcrList                : {}
AppType                : PrimaryVolume
DataContainer          : Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainer
DataContainerId        : 68b63d15-6aa5-4e69-9f9d-4a0bc607d6e9
InstanceId             : SS-VOL-d73b7eec-76fc-4310-b347-69b160de8cdd
InternalInstanceId     : 
IsBackupEnabled        : False
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
Name                   : Volume22
Online                 : True
OperationInProgress    : None
SizeInBytes            : 2000000000
VSN                    : SS-VOL-d73b7eec-76fc-4310-b347-69b160de8cdd

VERBOSE: Volume container with name: VolumeContainer01 is found.
```

This command gets the volume container named VolumeContainer01 for the device named Contoso63-AppVm by using the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.
The command passes that container to the current cmdlet by using the pipeline operator.
This cmdlet creates the volume.
The command specifies the name for the volume, the size, and an empty value for access control records.
This command specifies the *WaitForComplete* parameter, so it returns a **TaskStatusInfo** after it creates the volume.

Because the command specifies no access control records, this volume cannot be accessed.
You can add access, later, by using **Set-AzureStorSimpleDeviceVolume** cmdlet.

## PARAMETERS

### -AccessControlRecords
Specifies a list of access control records to associate with the volume.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to create the volume.

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

### -EnableDefaultBackup
Specifies whether to enable default backup for the volume.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableMonitoring
Specifies whether to enable monitoring for the volume.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Specifies whether to create the volume online.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
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

### -VolumeAppType
Specifies whether to create a primary or archive volume.
Valid values are: PrimaryVolume and ArchiveVolume.

```yaml
Type: AppType
Parameter Sets: (All)
Aliases: AppType
Accepted values: Invalid, PrimaryVolume, ArchiveVolume

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeContainer
Specifies the container, as a **DataContainer** object, in which to create the volume.
To obtain a **VirtualDisk** object, use the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.

```yaml
Type: DataContainer
Parameter Sets: (All)
Aliases: Container

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeName
Specifies a name for the new volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeSizeInBytes
Specifies the volume size in bytes.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: SizeInBytes

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
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DataContainer, List<AccessControlRecord>
This cmdlet accepts a **DataContainer** object and a list of **AccessControlRecord** objects for the new volume.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolume](.\Get-AzureStorSimpleDeviceVolume.md)

[Remove-AzureStorSimpleDeviceVolume](.\Remove-AzureStorSimpleDeviceVolume.md)

[Set-AzureStorSimpleDeviceVolume](.\Set-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

