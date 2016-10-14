---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleDeviceVolume.md
schema: 2.0.0
---

# Get-AzureStorSimpleDeviceVolume

## SYNOPSIS
Gets volumes on a device.

## SYNTAX

### IdentifyByParentObject
```
Get-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-VolumeContainer] <DataContainer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Get-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-VolumeName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDeviceVolume** cmdlet gets a list of volumes for a specified volume container, or volume that has the specified name.
The returned object contains the following properties: 

- **AccessType**
- **AcrList**
- **AppType**
- **DataContainer**
- **DataContainerId**
- **InstanceId**
- **IsBackupEnabled**
- **IsDefaultBackupEnabled**
- **IsMonitoringEnabled**
- **Name**
- **Online**
- **OperationInProgress**
- **SizeInBytes**
- **VSN**

## EXAMPLES

### Example 1: Get volumes in a specified container
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container03" | Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm"
InstanceId             : BA-1503262017214433280-ade42af6-dabb-449d-b66b-4f5d06891d4c
Name                   : Volume 1 Clone
Online                 : True
SizeInBytes            : 3298534883328
AccessType             : ReadWrite
AcrList                : {Windows_XYUSFL718-RV_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : BA-1503262017214433280-ade42af6-dabb-449d-b66b-4f5d06891d4c

InstanceId             : BA-1503262017366008684-cf8bb1a3-21e5-4cfc-ba0d-bfe238d77ebe
Name                   : Volume 3 Clone
Online                 : True
SizeInBytes            : 1717986918400
AccessType             : ReadWrite
AcrList                : {Linux_XYUSFL719_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : BA-1503262017366008684-cf8bb1a3-21e5-4cfc-ba0d-bfe238d77ebe

InstanceId             : SS-VOL-2180be94-36f1-473e-a42b-a3ebd2cdb481
Name                   : Volume 4
Online                 : True
SizeInBytes            : 1610612736000
AccessType             : ReadWrite
AcrList                : {Linux_XYUSFL719_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : SS-VOL-2180be94-36f1-473e-a42b-a3ebd2cdb481
```

This command gets the volume container named Container03 on the device named Contoso63-AppVm by using the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.
The command uses the pipeline operator to pass that container to the current cmdlet.
That cmdlet gets all the volumes in that container for the device named Contoso63-AppVm.

### Example 2: Get a volume by using its name
```
PS C:\>Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18"
InstanceId             : SS-VOL-c75e9636-1dcf-43db-92df-3af1ecf3f18a
Name                   : Volume18
Online                 : True
SizeInBytes            : 2748779069440
AccessType             : ReadWrite
AcrList                : {Windows_XYUSFL718-RV_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : SS-VOL-c75e9636-1dcf-43db-92df-3af1ecf3f18a
```

This command gets the volume named Volume18 on the device named Contoso63-AppVm.

## PARAMETERS

### -DeviceName
Specifies the name of the StorSimple device from which to get volumes.

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

### -VolumeContainer
Specifies the volume container, as a **DataContainer** object, that includes the volumes to get.
To obtain a **DataContainer**, use the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.

```yaml
Type: DataContainer
Parameter Sets: IdentifyByParentObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeName
Specifies the name of the volume to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DataContainer
This cmdlet accepts a **DataContainer** object that contains the volume to get.

## OUTPUTS

### VirtualDisk, IList<VirtualDisk>
This cmdlet returns a **VirtualDisk** object if you specify the *VolumeName* parameter.
If you specify the *VolumeContainer*, this cmdlet returns an **IList\<VirtualDisk\>** object.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceVolume](.\New-AzureStorSimpleDeviceVolume.md)

[Remove-AzureStorSimpleDeviceVolume](.\Remove-AzureStorSimpleDeviceVolume.md)

[Set-AzureStorSimpleDeviceVolume](.\Set-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

