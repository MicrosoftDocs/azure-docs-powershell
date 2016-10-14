---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleAccessControlRecord.md
schema: 2.0.0
---

# Get-AzureStorSimpleDeviceConnectedInitiator

## SYNOPSIS
Gets the iSCSI connections available for a StorSimple device.

## SYNTAX

### IdentifyById
```
Get-AzureStorSimpleDeviceConnectedInitiator [-DeviceId] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### IdentifyByName
```
Get-AzureStorSimpleDeviceConnectedInitiator [-DeviceName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDeviceConnectedInitiator** cmdlet gets a list of the iSCSI connections available for a StorSimple device.
The iSCSI connection objects that this cmdlet returns contain the following properties:

- **AcrInstanceId**
- **AcrName**
- **AllowedVolumeNames**
- **InitiatorAddress**
- **Interfaces**
- **Iqn**
- **IscsiConnectionId**

This cmdlet gets connection object only if iSCSI connections are turned on for the device.
By default, connections are turned off.

## EXAMPLES

### Example 1: Get all connections for a device
```
PS C:\>Get-AzureStorSimpleDeviceConnectedInitiator -DeviceName "Contoso63-AppVm"
VERBOSE: ClientRequestId: bec615b9-79ab-4671-88b0-287adeb6bf68_PS
VERBOSE: ClientRequestId: ef976c58-2660-41c8-aa15-c84e70c9d01c_PS
VERBOSE: ClientRequestId: 9b306b96-8e76-47ed-beda-d3bd2fb2bb82_PS
VERBOSE: ClientRequestId: 0f4fc743-0b60-45da-a45a-27f4b0f32bd2_PS

AcrInstanceId      : 55f24643-ab3a-4098-ade2-aa2b1a3ab18c
AcrName            : Contoso63-AppVm
AllowedVolumeNames : {Policyvolume1_Default}
InitiatorAddress   : 
Interfaces         : {Data0}
Iqn                : iqn10
IscsiConnectionId  : cfc144cb-00f1-44b1-9655-80b431f2161b

VERBOSE: 1 Iscsi Connection found!
```

This command gets all iSCSI connections for the device named Contoso63-AppVm.
This command returns connections only if connections are turned on for the device.

## PARAMETERS

### -DeviceId
Specifies the instance ID of the StorSimple device from which to get iSCSI initiators.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: ID

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device from which to get iSCSI initiators.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### List<IscsiConnection>
This cmdlet returns an iSCSI connection object that contains the following properties: 

- **AcrInstanceId**
- **AcrName**
- **AllowedVolumeNames**
- **InitiatorAddress**
- **Interfaces**
- **Iqn**
- **IscsiConnectionId**

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

