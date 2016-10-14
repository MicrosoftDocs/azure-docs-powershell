---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleDeviceVolumeContainer.md
schema: 2.0.0
---

# Get-AzureStorSimpleDeviceVolumeContainer

## SYNOPSIS
Gets volume containers on a device.

## SYNTAX

```
Get-AzureStorSimpleDeviceVolumeContainer [-DeviceName] <String> [[-VolumeContainerName] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet gets a list of volume containers on a device, or volume container that has the specified name.
The returned object contains the following properties: 

- **BandwidthRate**
- **EncryptionKey**
- **InstanceId**
- **IsDefault**
- **IsEncryptionEnabled**
- **Name**
- **OperationInProgress**
- **Owned**
- **PrimaryStorageAccountCredential**
- **SecretsEncryptionThumbprint**
- **VolumeCount**

## EXAMPLES

### Example 1: Get all the containers on a device
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "8600-Bravo 001"
InstanceId                           Name                                             IsEncryptionEnabled  Owned BandwidthRate                                    PrimaryStorageAccountCredential                 VolumeCount                                    
----------                           ----                                             -------------------  ----- -------------                                    -------------------------------                 -----------                                    
127135b6-92de-4f53-850d-70e1f9a38cbe Test_Container                                   False                True  0                                                Test_Account                                    6
```

This command gets a list of the volume containers on the device named 8600-Bravo 001.

### Example 2: Get a container by using its name
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container08"
VERBOSE: ClientRequestId: 8027c66a-869b-4ea3-97a2-e17d98ec751c_PS
VERBOSE: ClientRequestId: 344f9be5-0887-4d37-98ef-e45c557774f1_PS
VERBOSE: ClientRequestId: 14919be5-d6f5-4f81-b7f1-d7fafff2238c_PS


BandwidthRate                   : 256
EncryptionKey                   : 
InstanceId                      : 04ea9aad-7a56-4a50-b195-86061b0a810a
IsDefault                       : False
IsEncryptionEnabled             : False
Name                            : Container03
OperationInProgress             : None
Owned                           : True
PrimaryStorageAccountCredential : Microsoft.WindowsAzure.Management.StorSimple.Models.StorageAccountCredentialResponse
SecretsEncryptionThumbprint     : 
VolumeCount                     : 5

VERBOSE: Volume container with name: Container03 is found.
```

This command gets the volume container named Container08 on the device named Contoso63-AppVm.

## PARAMETERS

### -DeviceName
Specifies the name of a StorSimple device.
This cmdlet gets volume containers from the device that this parameter specifies.

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

### -VolumeContainerName
Specifies the name of the volume container to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### DataContainer, IList<DataContainer>
This cmdlet returns a **DataContainer** object, if you specify the *VolumeContainerName* parameter.
If you do not specify that parameter, this cmdlet returns an **IList\<DataContainer\>** object.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceVolumeContainer](.\New-AzureStorSimpleDeviceVolumeContainer.md)

[Remove-AzureStorSimpleDeviceVolumeContainer](.\Remove-AzureStorSimpleDeviceVolumeContainer.md)

