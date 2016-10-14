---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceVolume.md
schema: 2.0.0
---

# Set-AzureStorSimpleDeviceVolume

## SYNOPSIS
Updates the properties of an existing volume.

## SYNTAX

### IdentifyByName
```
Set-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-VolumeName] <String> [[-Online] <Boolean>]
 [[-VolumeSizeInBytes] <Int64>] [[-VolumeAppType] <AppType>]
 [[-AccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-WaitForComplete] [[-NewName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Set-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-Volume] <VirtualDisk> [[-Online] <Boolean>]
 [[-VolumeSizeInBytes] <Int64>] [[-VolumeAppType] <AppType>]
 [[-AccessControlRecords] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-WaitForComplete] [[-NewName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleDeviceVolume** cmdlet updates the properties of an existing volume.
This cmdlet associates a volume with one or more access control records.
To obtain **AccessControlRecord** objects, use the **Get-AzureStorSimpleAccessControlRecord** cmdlet.
Update the size or type for the volume.
Also, update whether to create the volume online.

## EXAMPLES

### Example 1: Update online value for a volume
```
PS C:\>Set-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" -Online $False
VERBOSE: ClientRequestId: f2869570-ea47-4be7-801e-9c0f22f2600d_PS
VERBOSE: ClientRequestId: c70bb86a-51d3-4390-be17-4d0847641dc3_PS
VERBOSE: ClientRequestId: d20cb5b2-6b3c-4e06-af99-cada28c5e50a_PS
VERBOSE: ClientRequestId: ab6d533e-b55b-4cfb-9c58-9153295e0547_PS
de7000f1-29c7-4102-a375-b52432f9e67e
VERBOSE: The update task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
de7000f1-29c7-4102-a375-b52432f9e67e for tracking the task's status
```

This command updates the volume named Volume18 to have an online value of $False.
This command starts the task, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.

### Example 2: Modify online value and type
```
PS C:\>Set-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" -Online $True -VolumeAppType ArchiveVolume 
VERBOSE: ClientRequestId: af42b02a-645e-4801-a2d7-4197511c68cf_PS
VERBOSE: ClientRequestId: 7cb4f3b4-548e-42dc-a38c-0df0911c5206_PS
VERBOSE: ClientRequestId: 7cc706ad-a58f-4939-8e78-cabae8379a51_PS
VERBOSE: ClientRequestId: 6bed21d5-12fc-4a12-a89c-120bdb5636b1_PS
aa977225-af78-4c93-b754-72704afc928f
VERBOSE: The update task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
aa977225-af78-4c93-b754-72704afc928f for tracking the task's status
```

This command updates the volume named Volume18.
It modifies the type and changes the value of the *Online* parameter to $True.

## PARAMETERS

### -AccessControlRecords
Specifies a list of access control records to associate with the volume.

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

### -DeviceName
Specifies the name of the StorSimple device on which to update the volume exists.

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
Specifies a new name for the StorSimple device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Specifies whether the volume is online.

```yaml
Type: Boolean
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
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies the name of the volume to update.

```yaml
Type: VirtualDisk
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeAppType
Specifies whether to update the volume to be a primary or archive volume.
Valid values are: PrimaryVolume and ArchiveVolume.

```yaml
Type: AppType
Parameter Sets: (All)
Aliases: AppType
Accepted values: PrimaryVolume, ArchiveVolume

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeName
Specifies the name of the volume to update.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeSizeInBytes
Specifies the updated size, in bytes, for the volume.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: SizeInBytes

Required: False
Position: 4
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
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### List<AccessControlRecord>
This cmdlet accepts a list of **AccessControlRecord** objects to associate to a volume.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolume](.\Get-AzureStorSimpleDeviceVolume.md)

[New-AzureStorSimpleDeviceVolume](.\New-AzureStorSimpleDeviceVolume.md)

[Remove-AzureStorSimpleDeviceVolume](.\Remove-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

