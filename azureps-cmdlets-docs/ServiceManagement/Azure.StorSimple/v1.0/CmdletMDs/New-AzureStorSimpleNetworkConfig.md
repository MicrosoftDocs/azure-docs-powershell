---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Set-AzureStorSimpleDevice.md
schema: 2.0.0
---

# New-AzureStorSimpleNetworkConfig

## SYNOPSIS
Prepares a network configuration object.

## SYNTAX

```
New-AzureStorSimpleNetworkConfig [-InterfaceAlias] <String> [[-EnableIscsi] <Boolean>]
 [[-EnableCloud] <Boolean>] [[-Controller0IPv4Address] <String>] [[-Controller1IPv4Address] <String>]
 [[-IPv6Gateway] <String>] [[-IPv4Gateway] <String>] [[-IPv4Address] <String>] [[-IPv6Prefix] <String>]
 [[-IPv4Netmask] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleNetworkConfig** cmdlet prepares a network configuration object to pass to the **Set-AzureStorSimpleDevice** cmdlet.
Set the *Controller0IPAddress* parameter and *Controller1IPAddress* parameter only on the Data0 interface.
Data0 supports only three settings: *Controller0IPAddress*, *Controller1IPAdress*, and *EnableIscsi*.

## EXAMPLES

### Example 1: Configure a Data0 interface
```
PS C:\>New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49"
VERBOSE: ClientRequestId: 0621d220-a460-48ec-84ec-02a3a82f88b2_PS


IsIscsiEnabled         : True
IsCloudEnabled         : 
Controller0IPv4Address : 10.67.64.48
Controller1IPv4Address : 10.67.64.49
IPv6Gateway            : 
IPv4Gateway            : 
IPv4Address            : 
IPv6Prefix             : 
IPv4Netmask            : 
InterfaceAlias         : Data0

VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
```

This command creates network configuration for the Data0 interface.
This command specifies the *Controller0IPv4Address*, *Controller1IPv4Address*, and *EnableIscsi* parameters.
This cmdlet can configure Data0 for only these three parameters.

### Example 2: Configuren an interface other than Data0 an
```
PS C:\>New-AzureStorSimpleNetworkConfig -InterfaceAlias Data1 -EnableIscsi $True -EnableCloud $True -IPv6Gateway "db8:421e:9a8::a4:1c50" -IPv4Gateway "10.67.64.1" -IPv4Address "10.67.64.48" -IPv6Prefix "2001:db8:a::123/64" -IPv4Netmask "255.255.0.0"
VERBOSE: ClientRequestId: 3a15ff0e-b769-4329-9147-676b1e0acd7d_PS


IsIscsiEnabled         : True
IsCloudEnabled         : True
Controller0IPv4Address : 
Controller1IPv4Address : 
IPv6Gateway            : db8:421e:9a8::a4:1c50
IPv4Gateway            : 10.67.64.1
IPv4Address            : 10.67.64.48
IPv6Prefix             : 2001:db8:a::123/64
IPv4Netmask            : 255.255.0.0
InterfaceAlias         : Data1
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data1
```

This command configures the Data1 interface.

### Example 3: Modify a configuration for a device
```
PS C:\>$NetworkConfigData0 = New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49"
$OnlineDevice = @(Get-AzureStorSimpleDevice | Where { $_.Status -eq "Online"})[0]
$UpdatedDetails = Set-AzureStorSimpleDevice -DeviceId $OnlineDevice.DeviceId -StorSimpleNetworkConfig $NetworkConfigData0
VERBOSE: ClientRequestId: 0f163163-5ad0-4635-a7b5-870d47297f66_PS
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
VERBOSE: ClientRequestId: 552e4a6c-7006-4015-a20b-9def6428a85e_PS
VERBOSE: ClientRequestId: f31cc84c-bc8a-404a-9da6-4670a7999e75_PS
VERBOSE: 1 StorSimple device found! 
VERBOSE: ClientRequestId: 545bc1a9-3c1b-4e50-89a6-9678aefe79e5_PS
VERBOSE: ClientRequestId: f114ad08-47f5-4fb8-8a01-1ea7f1ed1b98_PS
VERBOSE: About to configure the device : newDeviceName ! 
VERBOSE: ClientRequestId: 6afe7927-1c19-48d3-ac22-68148fd056b8_PS
VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: 467c142c-90da-4d75-82a4-c114afce953d_PS
VERBOSE: Successfully updated configuration for device newDeviceName with id 865e68f6-1e71-47b6-80d5-15d3a23bd2b0
```

The first command creates a network configuration for the Data0 interface.
This command specifies the *Controller0IPv4Address*, *Controller1IPv4Address*, and *EnableIscsi* parameters.
The command stores the result in the $NetworkConfigData0 variable.

The second command uses the **Get-AzureStorSimpleDevice** cmdlet and the **Where-Object** core cmdlet to get an online StorSimple device, and then stores it in the $OnlineDevice variable.

The final command modifies the configuration for the device that has the specified device ID by using the **Set-AzureStorSimpleDevice** cmdlet.
The command uses the configuration object that the current cmdlet created in the first command.

## PARAMETERS

### -Controller0IPv4Address
Specifies the IPv4 address for controller 0.
Specify this parameter only for the Data0 interface.

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

### -Controller1IPv4Address
Specifies the IPv4 address for controller 1.
Specify this parameter only for the Data0 interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCloud
Indicates whether to cloud-enable the interface.

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

### -EnableIscsi
Indicates whether to enable Internet SCSI (ISCSI) for the interface.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the interface alias of interface for which this cmdlet supplies settings.
Valid values are from Data0 to Data5.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Data0, Data1, Data2, Data3, Data4, Data5

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Specifies the IPv4 address for the interface.

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

### -IPv4Gateway
Specifies the IPv4 address of a gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Netmask
Specifies the IPv4 netmask for the interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Gateway
Specifies the IPv6 gateway for the interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Prefix
Specifies the IPv6 prefix for the interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
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

### NetworkConfig
This cmdlet returns a NetworkConfig object that contains the following properties: 

- **IsIscsiEnabled** (**Boolean**) 
- **IsCloudEnabled** (**Boolean**)
- **Controller0IPv4Address** (**IPAddress**) 
- **Controller1IPv4Address** (**IPAddress**) 
- **IPv6Gateway** (**IPAddress**) 
- **IPv4Gateway** (**IPAddress**) 
- **IPv4Address** (**IPAddress**) 
- **IPv6Prefix** (**String**)
- **IPv4Netmask** (**IPAddress**) 
- **InterfaceAlias** (**NetInterfaceId**)

## NOTES

## RELATED LINKS

[Set-AzureStorSimpleDevice](.\Set-AzureStorSimpleDevice.md)

[Get-AzureStorSimpleDevice](.\Get-AzureStorSimpleDevice.md)

