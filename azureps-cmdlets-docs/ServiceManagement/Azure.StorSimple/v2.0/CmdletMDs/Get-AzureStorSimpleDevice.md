---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleResourceContext.md
schema: 2.0.0
---

# Get-AzureStorSimpleDevice

## SYNOPSIS
Gets devices attached to the resource.

## SYNTAX

### Empty (Default)
```
Get-AzureStorSimpleDevice [[-Type] <String>] [[-ModelID] <String>] [-Detailed] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### IdentifyById
```
Get-AzureStorSimpleDevice [[-DeviceId] <String>] [[-Type] <String>] [[-ModelID] <String>] [-Detailed]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Get-AzureStorSimpleDevice [[-DeviceName] <String>] [[-Type] <String>] [[-ModelID] <String>] [-Detailed]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDevice** cmdlet gets a list of StorSimple devices attached to the resource.
You can specify device ID, name, model ID, and type.
Use the **DeviceID** property obtained by using this cmdlet to specify devices for other StorSimple cmdlets.

## EXAMPLES

### Example 1: Get available devices on a resource
```
PS C:\>Get-AzureStorSimpleDevice
DeviceId                  : 6f9ab151-39c7-4ded-b7d0-f5b0968f2766
DeviceName                : 8600-: SHX0881018G88
SerialNumber              : SHX0881018G88
DeviceSoftwareVersion     : 6.3.9600.17430
Location                  : 
ModelDescription          : 8600
Status                    : Offline
Type                      : Appliance
TargetIQN                 : iqn.1991-05.com.microsoft:storsimple8600-shx0991018g00e4-target
TimeZone                  : Pacific Standard Time
ActivationTime            : 2015-04-07T16:32:30.2960842Z
AvailableStorageInBytes   : 535363378479104
ProvisionedStorageInBytes : 14392435408896
TotalStorageInBytes       : 549755813888000
UsingStorageInBytes       : 12693995520

DeviceId                  : eb30ea31-c856-4cf2-9a02-aee611d6a3b9
DeviceName                : 8100-Delta 001
SerialNumber              : SHX90391XXXXXXX
DeviceSoftwareVersion     : 6.3.9600.17430
Location                  : 
ModelDescription          : 8100
Status                    : Online
Type                      : Appliance
TargetIQN                 : iqn.1991-05.com.microsoft:storsimple8100-shx90193xxxxxxx-target
TimeZone                  : Eastern Standard Time
ActivationTime            : 2015-03-26T14:53:14.4219391Z
AvailableStorageInBytes   : 205509890146304
ProvisionedStorageInBytes : 14392435408896
TotalStorageInBytes       : 219902325555200
UsingStorageInBytes       : 23904321536

DeviceId                  : edcb0b9b-1ed5-4102-9c5d-c589f7632994
DeviceName                : 8600-Bravo 001
SerialNumber              : SHX0900915G44SY
DeviceSoftwareVersion     : 6.3.9600.17430
Location                  : 
ModelDescription          : 8600
Status                    : Online
Type                      : Appliance
TargetIQN                 : iqn.1991-05.com.microsoft:storsimple8600-shx0900915g44sy-target
TimeZone                  : Eastern Standard Time
ActivationTime            : 2015-03-26T15:36:26.0870525Z
AvailableStorageInBytes   : 535363378479104
ProvisionedStorageInBytes : 14392435408896
TotalStorageInBytes       : 549755813888000
UsingStorageInBytes       : 978893799424
```

This command gets all available devices on a resource.
In this example, only one device is available.

### Example 2: Get specific available devices on a resource
```
PS C:\>Get-AzureStorSimpleDevice -DeviceName "8600-SHX90193XXXXXXX" -Type Appliance -ModelId "8600"
DeviceId                  : f9db31da-8a6c-4718-8f5b-5ce89e600f28
DeviceName                : 8600-SHX90193XXXXXXX
SerialNumber              : SHX90193XXXXXXX
DeviceSoftwareVersion     : 6.3.9600.17430
Location                  : 
ModelDescription          : 8600
Status                    : Online
Type                      : Appliance
TargetIQN                 : iqn.1991-05.com.microsoft:storsimple8600-shx90193xxxxxxx-target
TimeZone                  : Pacific Standard Time
ActivationTime            : 2015-04-07T18:10:46.4524766Z
AvailableStorageInBytes   : 535363378479104
ProvisionedStorageInBytes : 14392435408896
TotalStorageInBytes       : 549755813888000
UsingStorageInBytes       : 14445182976
```

This command gets all available devices on a resource that have the specified name, type, and model ID.

### Example 3: Get details for a device
```
PS C:\>Get-AzureStorSimpleDevice -Name "8600-SHX90193XXXXXXX" -Type Appliance -Detailed
AlertNotification              : Microsoft.WindowsAzure.Management.StorSimple.Models.AlertNotificationSettings
Chap                           : Microsoft.WindowsAzure.Management.StorSimple.Models.ChapSettings
DeviceProperties               : Microsoft.WindowsAzure.Management.StorSimple.Models.DeviceInfo
DnsServer                      : Microsoft.WindowsAzure.Management.StorSimple.Models.DnsServerSettings
InstanceId                     : f9db31da-8a6c-4718-8f5b-5ce89e600f28
Name                           : 
NetInterfaceList               : {Data0, Data1, Data2, Data3...} 
OperationInProgress            : None
RemoteMgmtSettingsInfo         : Microsoft.WindowsAzure.Management.StorSimple.Models.RemoteManagementSettings

RemoteMinishellSecretInfo      : Microsoft.WindowsAzure.Management.StorSimple.Models.RemoteMinishellSettings
SecretEncryptionCertThumbprint : 
Snapshot                       : Microsoft.WindowsAzure.Management.StorSimple.Models.SnapshotSettings
TimeServer                     : Microsoft.WindowsAzure.Management.StorSimple.Models.TimeSettings
Type                           : Appliance
VirtualApplianceProperties     : Microsoft.WindowsAzure.Management.StorSimple.Models.VirtualApplianceInfo
WebProxy                       : Microsoft.WindowsAzure.Management.StorSimple.Models.WebProxySettings
```

This command gets all available devices on a resource that have the specified name and type.
This command specifies the *Detailed* parameter.
The command provides additional details about the devices it returns.

## PARAMETERS

### -Detailed
Indicates that this cmdlet returns device details for the devices that it gets.

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

### -DeviceId
Specifies the instance ID of the device to get.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: ID

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device to get.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModelID
Specifies the ID of the model of StorSimple devices to get.

```yaml
Type: String
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

### -Type
Specifies the type of a StorSimple device.
Valid values are: Appliance and VirtualAppliance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Appliance, VirtualAppliance

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

### List<DeviceDetails>, IEnumerable<DeviceInfo>
This cmdlet returns a **List\<DeviceDetails\>** object, if you specify the *Detailed* parameter.
If you do not specify that parameter, it returns an **IEnumerable\<DeviceInfo\>** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleResourceContext](.\Get-AzureStorSimpleResourceContext.md)

[Select-AzureStorSimpleResource](.\Select-AzureStorSimpleResource.md)

