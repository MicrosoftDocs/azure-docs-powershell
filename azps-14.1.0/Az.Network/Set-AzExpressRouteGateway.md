---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/set-azexpressroutegateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzExpressRouteGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzExpressRouteGateway.md
---

# Set-AzExpressRouteGateway

## SYNOPSIS
Updates a Scalable ExpressRoute Gateway.

## SYNTAX

### ByExpressRouteGatewayName (Default)
```
Set-AzExpressRouteGateway -ResourceGroupName <String> -Name <String> [-MinScaleUnits <UInt32>]
 [-MaxScaleUnits <UInt32>] [-AllowNonVirtualWanTraffic <Boolean>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByExpressRouteGatewayObject
```
Set-AzExpressRouteGateway -InputObject <PSExpressRouteGateway> [-MinScaleUnits <UInt32>]
 [-MaxScaleUnits <UInt32>] [-AllowNonVirtualWanTraffic <Boolean>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByExpressRouteGatewayResourceId
```
Set-AzExpressRouteGateway -ResourceId <String> [-MinScaleUnits <UInt32>] [-MaxScaleUnits <UInt32>]
 [-AllowNonVirtualWanTraffic <Boolean>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Set-AzExpressRouteGateway** cmdlet enables you to update the scale units for an existing ExpressRouteGateway or update the resource tags.

## EXAMPLES

### Example 1

```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$virtualWan = New-AzVirtualWan -ResourceGroupName testRG -Name myVirtualWAN -Location "West US"
$virtualHub = New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.0.1/24"
New-AzExpressRouteGateway -ResourceGroupName "testRG" -Name "testergw" -VirtualHubId $virtualHub.Id -MinScaleUnits 2
Set-AzExpressRouteGateway -ResourceGroupName "testRG" -Name "testergw" -MinScaleUnits 3
```

```output
ResourceGroupName   : testRG
Name                : testergw
Id                  : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/expressRouteGateways/testergw
Location            : West US
MinScaleUnits       : 3
Type                : Microsoft.Network/expressRouteGateways
ProvisioningState   : Succeeded
```

The above will create a resource group "testRG", a Virtual WAN and a Virtual Hub in West US in that resource group in Azure.
An ExpressRoute gateway will be created thereafter in the Virtual Hub with 2 scale units which will then be modified to 3 scale units.

### Example 2: Configure this gateway to accept traffic from non Virtual Wan networks.
You may either retrieve the gateway, configure its AllowNonVirtualWanTraffic property and save the changes on the gateway or you may just use the switch on the Set-AzExpressRouteGateway cmdlet

```powershell
# Option 1 - Retrieve the gateway object, configure it to allow traffic from VNets and persist those changes.  
$gateway = Get-AzExpressRouteGateway -ResourceGroupName "resourceGroup001" -Name "gateway001"
$gateway.AllowNonVirtualWanTraffic = $true
$gateway = Set-AzExpressRouteGateway -InputObject $gateway

# Option 2 - Use the cmdlet switch
Set-AzExpressRouteGateway -ResourceGroupName "resourceGroup001" -Name "gateway001" -AllowNonVirtualWanTraffic $true
```

### Example 3: Configure this gateway to block traffic from non Virtual Wan networks.
You may either retrieve the gateway, configure its AllowNonVirtualWanTraffic property and save the changes on the gateway or you may just use the switch on the Set-AzExpressRouteGateway cmdlet

```powershell
# Option 1 - Retrieve the gateway object, configure it to block traffic from VNets and persist those changes.  
$gateway=Get-AzExpressRouteGateway -ResourceGroupName "resourceGroup001" -Name "gateway001"
$gateway.AllowNonVirtualWanTraffic = $false
$gateway = Set-AzExpressRouteGateway -InputObject $gateway

# Option 2 - Use the cmdlet switch
Set-AzExpressRouteGateway -ResourceGroupName "resourceGroup001" -Name "gateway001" -AllowNonVirtualWanTraffic $false
```

## PARAMETERS

### -AllowNonVirtualWanTraffic
Determines whether this gateway should accept traffic from other VNets

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Run cmdlet in the background

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

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

### -InputObject
The ExpressRouteGateway that needs to be updated.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRouteGateway
Parameter Sets: ByExpressRouteGatewayObject
Aliases: ExpressRouteGateway

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxScaleUnits
The maximum number of scale units for this ExpressRouteGateway. Valid range > 2

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinScaleUnits
The minimum number of scale units for this ExpressRouteGateway. Valid range > 2

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The resource name.

```yaml
Type: System.String
Parameter Sets: ByExpressRouteGatewayName
Aliases: ResourceName, ExpressRouteGatewayName, GatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name of the ExpressRouteGateway to be updated.

```yaml
Type: System.String
Parameter Sets: ByExpressRouteGatewayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
The Id of the ExpressRouteGateway that needs to be updated.

```yaml
Type: System.String
Parameter Sets: ByExpressRouteGatewayResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
A hashtable which represents resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteGateway

## NOTES

## RELATED LINKS
