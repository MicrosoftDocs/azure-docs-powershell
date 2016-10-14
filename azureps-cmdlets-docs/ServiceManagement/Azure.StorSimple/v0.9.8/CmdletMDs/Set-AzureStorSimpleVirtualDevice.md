---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleVirtualDevice.md
schema: 2.0.0
---

# Set-AzureStorSimpleVirtualDevice

## SYNOPSIS
Creates or updates the device configuration of a StorSimple virtual device.

## SYNTAX

```
Set-AzureStorSimpleVirtualDevice [-DeviceName] <String> [-SecretKey] <String> [-AdministratorPassword] <String>
 [-SnapshotManagerPassword] <String> [[-TimeZone] <TimeZoneInfo>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleVirtualDevice** cmdlet creates or updates the device configuration of an Azure StorSimple virtual device.

## EXAMPLES

### Example 1: Update a virtual device
```
PS C:\>$TimeZoneInfo = [System.TimeZoneInfo]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" }
PS C:\> Set-AzureStorSimpleVirtualDevice -DeviceName "Contoso23" -SecretKey "wcZBlBGpCMf4USdSKyt/SQ==" -TimeZone $TimeZoneInfo
VERBOSE: ClientRequestId: e31f0d6b-451d-4c1d-b2f1-3fc84c13972c_PS
VERBOSE: ClientRequestId: df58db83-d563-4a2e-bbb4-9576f0e69ca6_PS
VERBOSE: ClientRequestId: 494a9f0d-79ee-4fde-ab4d-85ee5a357556_PS
VERBOSE: ClientRequestId: ce557cbf-174d-4301-93d4-5ffe082c8413_PS
VERBOSE: ClientRequestId: 31284dad-de2c-4758-a2ef-45962875bfa6_PS
VERBOSE: About to configure the device : win-ff93i74m1e1 ! 
VERBOSE: ClientRequestId: d9c66302-45d8-488a-adda-8ccf957f77d3_PS


TaskId       : 21f530c3-bc47-4591-8c4e-da4d694b751d
TaskResult   : Succeeded
TaskStatus   : Completed
ErrorCode    : 
ErrorMessage : 
TaskSteps    : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: a94f972c-18ea-40b6-9401-2ad209c0c8b4_PS
AlertNotification              : Microsoft.WindowsAzure.Management.StorSimple.Models.AlertNotificationSettings
Chap                           : Microsoft.WindowsAzure.Management.StorSimple.Models.ChapSettings
DeviceProperties               : Microsoft.WindowsAzure.Management.StorSimple.Models.DeviceInfo
DnsServer                      : Microsoft.WindowsAzure.Management.StorSimple.Models.DnsServerSettings
InstanceId                     : d369ebb4-8b9a-47fc-9a6b-60f371e123ae
Name                           : 
NetInterfaceList               : {}
OperationInProgress            : None
RemoteMgmtSettingsInfo         : Microsoft.WindowsAzure.Management.StorSimple.Models.RemoteManagementSettings
RemoteMinishellSecretInfo      : Microsoft.WindowsAzure.Management.StorSimple.Models.RemoteMinishellSettings
SecretEncryptionCertThumbprint : 
Snapshot                       : Microsoft.WindowsAzure.Management.StorSimple.Models.SnapshotSettings
TimeServer                     : Microsoft.WindowsAzure.Management.StorSimple.Models.TimeSettings
Type                           : VirtualAppliance
VirtualApplianceProperties     : Microsoft.WindowsAzure.Management.StorSimple.Models.VirtualApplianceInfo
WebProxy                       : Microsoft.WindowsAzure.Management.StorSimple.Models.WebProxySettings

VERBOSE: Successfully updated configuration for device Contoso23 with id d369ebb4-8b9a-47fc-9a6b-60f371e123ae
```

The first command uses the **System.TimeZoneInfo** .NET class and standard syntax to get Pacific Standard Time zone, and stores that object in the $TimeZoneInfo variable.

The second command updates the device named Contoso23 to use the time zone specified in $TimeZoneInfo.
The command requires the secret key to access the virtual device configuration.

### Example 2: Update a virtual device by using the pipeline operator
```
PS C:\> [System.TimeZoneInfo]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" } | Set-AzureStorSimpleVirtualDevice -DeviceName "Contoso23" -SecretKey "wcZBlBGpCMf4USdSKyt/SQ=="
```

This command updates the device named Contoso23 to use the time zone that the command creates.
The command requires the secret key to access the virtual device configuration.
This command works the same way as the previous example, except that it passes the time zone to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -AdministratorPassword
Specifies the administrator password of the virtual device to configure.

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

### -DeviceName
Specifies the name of the virtual device to configure.

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
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretKey
Specifies a service encryption key for the virtual device.
This key is generated when the first physical device is registered with a resource.

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

### -SnapshotManagerPassword
Specifies the snapshot manager password.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZone
Specifies a time zone for the device.
You can create a **TimeZoneInfo** object by using the **GetSystemTimeZone()** method.
For example, this command creates a time zone information object for Pacific Standard Time: `\[System.TimeZoneInfo\]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" }`

```yaml
Type: TimeZoneInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### TimeZoneInfo
You can pipe a **TimeZoneInfo** object to this cmdlet.

## OUTPUTS

### DeviceJobDetails
This cmdlet returns updated device details for the virtual device.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleVirtualDevice](.\New-AzureStorSimpleVirtualDevice.md)

[Set-AzureStorSimpleDevice](.\Set-AzureStorSimpleDevice.md)

