---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 356764CF-A860-432A-907A-9058CEB2BF8E
online version: https://docs.microsoft.com/powershell/module/az.network/new-azrouteconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRouteConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRouteConfig.md
---

# New-AzRouteConfig

## SYNOPSIS
Creates a route for a route table.

## SYNTAX

```
New-AzRouteConfig [-Name <String>] [-AddressPrefix <String>] [-NextHopType <String>]
 [-NextHopIpAddress <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzRouteConfig** cmdlet creates a route for an Azure route table.

## EXAMPLES

### Example 1: Create a route
```powershell
PS C:\>$Route = New-AzRouteConfig -Name "Route07" -AddressPrefix 10.1.0.0/16 -NextHopType "VnetLocal"
PS C:\> $Route
Name              : Route07
Id                : 
Etag              : 
ProvisioningState : 
AddressPrefix     : 10.1.0.0/16
NextHopType       : VnetLocal
NextHopIpAddress  :
```

The first command creates a route named Route07, and then stores it in the $Route variable.
This route forwards packets to the local virtual network.
The second command displays the properties of the route.

### Example 2

Creates a route for a route table. (autogenerated)

<!-- Aladdin Generated Example -->
```powershell
New-AzRouteConfig -AddressPrefix 10.1.0.0/16 -Name 'Route07' -NextHopIpAddress '12.0.0.5' -NextHopType 'VnetLocal'
```

### Example 3: Create a route with a Service Tag (Public Preview)
```powershell
New-AzRouteConfig -Name "Route07" -AddressPrefix "AppService" -NextHopType "VirtualAppliance" -NextHopIpAddress "10.0.2.4"
```

This command creates a route named Route07 which forwards traffic to IP prefixes contained in the AppService Service Tag to a virtual appliance. 

## PARAMETERS

### -AddressPrefix
Specifies the destination, in Classless Interdomain Routing (CIDR) format, to which the route applies. You can also specify a Service Tag here (this feature is in Public Preview).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the route.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopIpAddress
Specifies the IP address of a virtual appliance that you add to your Azurevirtual network.
This route forwards packets to that address.
Specify this parameter only if you specify a value of VirtualAppliance for the *NextHopType* parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHopType
Specifies how this route forwards packets.
The acceptable values for this parameter are:
- Internet.
The default Internet gateway provided by Azure. 
- None.
If you specify this value, the route does not forward packets. 
- VirtualAppliance.
A virtual appliance that you add to your Azure virtual network. 
- VirtualNetworkGateway.
An Azure server-to-server virtual private network gateway. 
- VnetLocal.
The local virtual network.
If you have two subnets, 10.1.0.0/16 and 10.2.0.0/16 in the same virtual network, select a value of VnetLocal for each subnet to forward to the other subnet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRoute

## NOTES

## RELATED LINKS

[Add-AzRouteConfig](./Add-AzRouteConfig.md)

[Get-AzRouteConfig](./Get-AzRouteConfig.md)

[Remove-AzRouteConfig](./Remove-AzRouteConfig.md)

[Set-AzRouteConfig](./Set-AzRouteConfig.md)

