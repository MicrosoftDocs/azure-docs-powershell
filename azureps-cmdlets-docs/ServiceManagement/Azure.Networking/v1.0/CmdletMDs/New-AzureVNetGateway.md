---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVNetGateway.md
schema: 2.0.0
---

# New-AzureVNetGateway

## SYNOPSIS
Creates a VPN gateway in a virtual network.

## SYNTAX

```
New-AzureVNetGateway [-VNetName] <String> [[-GatewayType] <String>] [[-GatewaySKU] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVNetGateway** cmdlet creates a virtual private network (VPN) gateway in a virtual network.
You can also specify the SKU of the gateway, either Default, Standard, or HighPerformance.
You can specify the type, either StaticRouting or DynamicRouting.

## EXAMPLES

### Example 1: Create a virtual network gateway
```
PS C:\>New-AzureVNetGateway -VNetName "ContosoVN07" -GatewayType "DynamicRouting" -GatewaySKU "Default"
```

This command creates a virtual network gateway for the virtual network named ContosoVN07.
The gateway is the Default SKU and uses dynamic routing.

## PARAMETERS

### -VNetName
Specifies the virtual network in which this cmdlet adds a virtual network gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayType
Specifies the type of gateway that this cmdlet creates.
Valid values are: 

- StaticRouting 
- DynamicRouting

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewaySKU
Specifies the SKU of the virtual network gateway that this cmdlet creates.
Valid values are: 

- Default 
- Standard 
- HighPerformance

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

## NOTES

## RELATED LINKS

[Get-AzureVNetGateway](.\Get-AzureVNetGateway.md)

[Remove-AzureVNetGateway](.\Remove-AzureVNetGateway.md)

[Reset-AzureVNetGateway](.\Reset-AzureVNetGateway.md)

[Resize-AzureVNetGateway](.\Resize-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](.\Set-AzureVNetGatewayKey.md)

