---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: BED3D3FE-D1E8-4857-A675-7B2670A129B2
online version: 
schema: 2.0.0
---

# New-AzureApplicationGateway

## SYNOPSIS
Creates an application gateway.

## SYNTAX

```
New-AzureApplicationGateway -Name <String> -VnetName <String>
 -Subnets <System.Collections.Generic.List`1[System.String]> [-InstanceCount <UInt32>] [-GatewaySize <String>]
 [-Description <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGateway** cmdlet creates an application gateway.

## EXAMPLES

### Example 1: Create an application gateway
```
PS C:\> New-AzureApplicationGateway -Name "ApplicationGateway06" -VnetName "VirutalNetwork17" -Subnets @("Subnet01", "Subnet02", "Subnet03")
```

This command creates an application gateway named ApplicationGateway06.
The command deploys the gateway in VirtualNetwork17 and in the specified subnets.

## PARAMETERS

### -Description
Specifies a description that this cmdlet assigns to the application gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewaySize
Specifies the size that this cmdlet assigns to the application gateway.
Valid values are:

- Small
- Medium
- Large

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceCount
Specifies the number of instances that this cmdlet assigns to the application gateway.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the new application gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -Subnets
Specifies an array of subnets in which this cmdlet deploys the application gateway.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VnetName
Specifies the virtual network in which this cmdlet deploys the application gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureApplicationGateway](./Get-AzureApplicationGateway.md)

[Remove-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](./Start-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](./Stop-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](./Update-AzureApplicationGateway.md)
