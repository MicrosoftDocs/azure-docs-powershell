---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppVNet.md
schema: 2.0.0
---

# Get-AzureRemoteAppVpnDevice

## SYNOPSIS
Retrieves information about a VPN device.

## SYNTAX

```
Get-AzureRemoteAppVpnDevice [-VNetName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppVpnDevice** cmdlet retrieves information about a virtual private network (VPN) device.

## EXAMPLES

### Example 1: Return the available VPN device configurations for a virtual network
```
PS C:\>Get-AzureRemoteVpnDevice -VNetName "ContosoVNet"


Name                   Platforms

----                   ---------

Cisco Systems, Inc.    {ASA 5500 Series Adaptive Security Appliances, ASR 1000 Series Aggregation Services Routers, ASR 1000 Series Aggregation Services Routers - Dynamic Routing, ISR Series Integrated Services Routers...} 

Juniper Networks, Inc. {SRX Series Routers, SRX Series Routers - Dynamic Routing, J Series Routers, J Series Routers - Dynamic Routing...} 

Microsoft Corporation  {RRAS}
```

This command returns the available VPN device configurations for the specified virtual network.

## PARAMETERS

### -VNetName
Specifies the name of the azure_2 RemoteApp virtual network.

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

### -Profile
ps_azureprofile_description

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

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppVNet](.\Get-AzureRemoteAppVNet.md)

[Get-AzureRemoteAppVpnDeviceConfigScript](.\Get-AzureRemoteAppVpnDeviceConfigScript.md)

