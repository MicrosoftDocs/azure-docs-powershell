---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleNetworkConfig.md
schema: 2.0.0
---

# Set-AzureStorSimpleDevice

## SYNOPSIS
Changes the device configuration for a device.

## SYNTAX

### IdentifyByName (Default)
```
Set-AzureStorSimpleDevice [-DeviceName] <String> [[-NewName] <String>] [[-TimeZone] <TimeZoneInfo>]
 [[-SecondaryDnsServer] <String>] [[-StorSimpleNetworkConfig] <NetworkConfig[]>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### IdentifyById
```
Set-AzureStorSimpleDevice [-DeviceId] <String> [[-NewName] <String>] [[-TimeZone] <TimeZoneInfo>]
 [[-SecondaryDnsServer] <String>] [[-StorSimpleNetworkConfig] <NetworkConfig[]>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleDevice** cmdlet changes the device configuration for a device.
If you are setting up a device for the first time, you must specify the *TimeZone*, *SecondaryDnsServer*, and *StorSimpleNetworkConfig* parameters.
You must include network configuration for Data0 with controller0 and controller1 and IP addresses.
There must be at least one Internet SCSI (ISCSI)-enabled network interface to configure the device for the first time.

## EXAMPLES

### Example 1: Modify the configuration for a device
```
PS C:\>$NetworkConfigData0 = New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49" 
PS C:\> $TimeZoneInfo = [System.TimeZoneInfo]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" }
PS C:\> $OnlineDevice = @(Get-AzureStorSimpleDevice | Where { $_.Status -eq "Online"})[0]
PS C:\> $UpdatedDetails = Set-AzureStorSimpleDevice -DeviceId $OnlineDevice.DeviceId -NewName "Device22" -TimeZone $TimeZoneInfo -SecondaryDnsServer 10.8.8.8 -StorSimpleNetworkConfig $NetworkConfigData0
VERBOSE: ClientRequestId: 0f163163-5ad0-4635-a7b5-870d47297f66_PS
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
VERBOSE: ClientRequestId: 552e4a6c-7006-4015-a20b-9def6428a85e_PS
VERBOSE: ClientRequestId: f31cc84c-bc8a-404a-9da6-4670a7999e75_PS
VERBOSE: 1 StorSimple device found! 
VERBOSE: ClientRequestId: 545bc1a9-3c1b-4e50-89a6-9678aefe79e5_PS
VERBOSE: ClientRequestId: f114ad08-47f5-4fb8-8a01-1ea7f1ed1b98_PS
VERBOSE: About to configure the device : Device22 ! 
VERBOSE: ClientRequestId: 6afe7927-1c19-48d3-ac22-68148fd056b8_PS
VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: 467c142c-90da-4d75-82a4-c114afce953d_PS
VERBOSE: Successfully updated configuration for device Device22 with id 865e68f6-1e71-47b6-80d5-15d3a23bd2b0
```

The first command creates a network configuration for the Data0 interface.
This command specifies the *Controller0IPv4Address*, *Controller1IPv4Address*, and *EnableIscsi* parameters.
The command stores the result in the $NetworkConfigData0 variable.

The second command uses the **System.TimeZoneInfo** .NET class and standard syntax to get Pacific Standard Time zone, and stores that object in the $TimeZoneInfo variable.

The third command uses the **Get-AzureStorSimpleDevice** cmdlet and the **Where-Object** core cmdlet to get an online StorSimple device, and then stores it in the $OnlineDevice variable.

The final command modifies the configuration for the device that has the specified device ID.
The command uses the configuration object that the current cmdlet created in the first command.
The command uses the time zone stored in $TimeZoneInfo.

### Example 2: Pipe the configuration object to modify a device
```
PS C:\>$TimeZoneInfo = [System.TimeZoneInfo]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" }
PS C:\> $OnlineDevice = @(Get-AzureStorSimpleDevice | Where { $_.Status -eq "Online"})[0]
PS C:\> $UpdatedDetails = New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49" | Set-AzureStorSimpleDevice -DeviceId $OnlineDevice.DeviceId -NewName "Device22" -TimeZone $TimeZoneInfo -SecondaryDnsServer 10.8.8.8 
VERBOSE: ClientRequestId: fa2f5000-169c-4feb-abbf-23f4b5c837fa_PS
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
VERBOSE: ClientRequestId: fae6a491-919c-44b2-93e0-0c51f202c24b_PS
VERBOSE: ClientRequestId: e1803427-a097-4d58-ab7d-14a4c39fd768_PS
VERBOSE: 1 StorSimple device found! 
VERBOSE: ClientRequestId: 9e796c3d-3100-46ab-9a09-0e10c73a296f_PS
VERBOSE: ClientRequestId: 5b4cad96-31f4-4d07-a278-df5af3e06ad4_PS
VERBOSE: About to configure the device : Device22 ! 
VERBOSE: ClientRequestId: 9061f7df-144f-4f30-858c-045d882ca392_PS
VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: 2ed2fa9b-8459-4cd6-9a61-5fc25ced2815_PS
VERBOSE: Successfully updated configuration for device Device22 with id 865e68f6-1e71-47b6-80d5-15d3a23bd2b0
```

This example does the same configuration update as the first example, except that the final command passes the network configuration object to the current cmdlet by using the pipeline operator.

### Example 3: Pipe the time zone object to modify a device
```
PS C:\>$NetworkConfigData0 = New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49" 
PS C:\> $OnlineDevice = @(Get-AzureStorSimpleDevice | Where { $_.Status -eq "Online"})[0]
PS C:\> $UpdatedDetails = [System.TimeZoneInfo]::GetSystemTimeZones() | where { $_.Id -eq "Pacific Standard Time" } | Set-AzureStorSimpleDevice -DeviceId $OnlineDevice.DeviceId -NewName "Device22" -SecondaryDnsServer 10.8.8.8 -StorSimpleNetworkConfig $NetworkConfigData0
VERBOSE: ClientRequestId: cfc3f3c7-a8b6-462b-96f4-124050b736fe_PS
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
VERBOSE: ClientRequestId: 6017b76f-a771-4bf8-901e-14876e0f9962_PS
VERBOSE: ClientRequestId: 59a9275c-9005-4e8a-b68b-efa1e6c27d47_PS
VERBOSE: 1 StorSimple device found! 
VERBOSE: ClientRequestId: 08e5142a-b038-4607-8690-0c5a8b948352_PS
VERBOSE: ClientRequestId: 218af244-b8f4-4a4b-817e-8f67e1323f03_PS
VERBOSE: About to configure the device : Device22 ! 
VERBOSE: ClientRequestId: fbd1f32d-1d74-432e-9dc0-90b46674884a_PS
VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: 981cb941-252c-4898-ba9f-f19e5b8bcaa4_PS
VERBOSE: Successfully updated configuration for device Device22 with id 865e68f6-1e71-47b6-80d5-15d3a23bd2b0
```

This example does the same configuration update as the first example, except that the final command passes the time zone object to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -DeviceId
Specifies the instance ID of the StorSimple device to configure.

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

### -DeviceName
Specifies the friendly name of the StorSimple device to configure.

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

### -NewName
Specifies the new friendly name of the StorSimple device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### -SecondaryDnsServer
Specifies a secondary DNS server for the StorSimple device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorSimpleNetworkConfig
Specifies an array of of network configuration objectss for interfaces on a device.
To obtain a **NetworkConfig** object, use the New-AzureStorSimpleNetworkConfig cmdlet.

```yaml
Type: NetworkConfig[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByValue)
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
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### NetworkConfig, TimeZoneInfo
You can pipe a **NetworkConfig** object or a **TimeZoneInfo** to this cmdlet.

## OUTPUTS

### DeviceDetails
This cmdlet returns updated device details for the virtual device.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleNetworkConfig](.\New-AzureStorSimpleNetworkConfig.md)

[Set-AzureStorSimpleVirtualDevice](.\Set-AzureStorSimpleVirtualDevice.md)

