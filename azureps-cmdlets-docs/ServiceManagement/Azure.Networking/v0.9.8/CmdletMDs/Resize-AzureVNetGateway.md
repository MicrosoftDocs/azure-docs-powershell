---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVNetGateway.md
schema: 2.0.0
---

# Resize-AzureVNetGateway

## SYNOPSIS
Resizes a VPN gateway.

## SYNTAX

```
Resize-AzureVNetGateway [-VNetName] <String> [-GatewaySKU] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Resize-AzureVNetGateway** cmdlet resizes a virtual network virtual private network (VPN) gateway to a different SKU.
Valid SKUs for a virtual network gateway are Default, Standard, and HighPerformance.

## EXAMPLES

### Example 1: Change the SKU for a virtual network gateway
```
PS C:\>Resize-AzureVNetGateway -VNetName "ContosoVN07" -GatewaySKU "HighPerformance"
```

This command changes the SKU of the virtual network gateway for the virtual network named ContosoVN07 to HighPerformance.

## PARAMETERS

### -VNetName
Specifies the virtual network in which this cmdlet resizes a virtual network gateway.

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

### -GatewaySKU
Specifies the SKU to which this cmdlet resizes virtual network gateway.
Valid values are: 

- Default 
- Standard 
- HighPerformance

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVNetGateway](.\Get-AzureVNetGateway.md)

[New-AzureVNetGateway](.\New-AzureVNetGateway.md)

[Remove-AzureVNetGateway](.\Remove-AzureVNetGateway.md)

[Reset-AzureVNetGateway](.\Reset-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](.\Set-AzureVNetGatewayKey.md)

