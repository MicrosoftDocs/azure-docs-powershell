---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppVpnDevice.md
schema: 2.0.0
---

# Get-AzureRemoteAppVpnDeviceConfigScript

## SYNOPSIS
Retrieves the configuration script for a RemoteApp VPN device.

## SYNTAX

```
Get-AzureRemoteAppVpnDeviceConfigScript [-VNetName] <String> [-Vendor] <String> [-Platform] <String>
 [-OSFamily] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppVpnDeviceConfigScript** cmdlet retrieves the configuration script for an Azure RemoteApp virtual private network (VPN) device.

## EXAMPLES

### Example 1: Get a configuration script for a VPN device
```
PS C:\>Get-AzureRemoteAppVpnDeviceConfigScript -VNetName "ContosoVNet" -Vendor "Microsoft Corporation" -OSFamily "Windows Server 2012 R2"
```

This command returns the script or configuration file used to configure the VPN device for the virtual network named ContosoVNet.
This script or configuration file should be run or loaded onto the VPN device in the typical manner for that device.
Consult the VPN device vendor for the unique requirements for each device.

## PARAMETERS

### -OSFamily
Specifies the operating system (OS) family that runs on the device platform.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Platform
Specifies the device platform.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -VNetName
Specifies the name of a RemoteApp virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Vendor
Specifies the vendor of the VPN device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppVpnDevice](.\Get-AzureRemoteAppVpnDevice.md)

