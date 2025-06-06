---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: D7065B04-1A01-4BB4-A519-1DA9002CDE02
online version: https://learn.microsoft.com/powershell/module/az.network/set-azvirtualnetworkgatewayconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetworkGatewayConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetworkGatewayConnection.md
---

# Set-AzVirtualNetworkGatewayConnection

## SYNOPSIS
Configures a virtual network gateway connection.

## SYNTAX

### Default (Default)
```
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection <PSVirtualNetworkGatewayConnection>
 [-EnableBgp <Boolean>] [-DpdTimeoutInSeconds <Int32>] [-ConnectionMode <String>]
 [-UsePolicyBasedTrafficSelectors <Boolean>] [-UseLocalAzureIpAddress <Boolean>]
 [-IpsecPolicies <PSIpsecPolicy[]>] [-TrafficSelectorPolicy <PSTrafficSelectorPolicy[]>]
 [-IngressNatRule <PSResourceId[]>] [-EgressNatRule <PSResourceId[]>]
 [-GatewayCustomBgpIpAddress <PSGatewayCustomBgpIpConfiguration[]>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateResourceWithTags
```
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection <PSVirtualNetworkGatewayConnection>
 [-EnableBgp <Boolean>] [-DpdTimeoutInSeconds <Int32>] [-ConnectionMode <String>]
 [-UsePolicyBasedTrafficSelectors <Boolean>] [-UseLocalAzureIpAddress <Boolean>]
 [-IpsecPolicies <PSIpsecPolicy[]>] [-TrafficSelectorPolicy <PSTrafficSelectorPolicy[]>]
 [-IngressNatRule <PSResourceId[]>] [-EgressNatRule <PSResourceId[]>]
 [-GatewayCustomBgpIpAddress <PSGatewayCustomBgpIpConfiguration[]>] -Tag <Hashtable> [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzVirtualNetworkGatewayConnection** cmdlet configures a virtual network gateway connection.

## EXAMPLES

### Example 1:
```powershell
$conn = Get-AzVirtualNetworkGatewayConnection -Name 1 -ResourceGroupName myRG
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection $conn
```

```output
Confirm
Are you sure you want to overwrite resource '1'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y


Name                    : 1
ResourceGroupName       : myRG
Location                : westus
Id                      : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Mi
                          crosoft.Network/connections/1
Etag                    : W/"00000000-0000-0000-0000-000000000000"
ResourceGuid            : 00000000-0000-0000-0000-000000000000
ProvisioningState       : Succeeded
Tags                    :
AuthorizationKey        :
VirtualNetworkGateway1  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/M
                          icrosoft.Network/virtualNetworkGateways/myGateway"
VirtualNetworkGateway2  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/S2SVnetConn/providers/Mic
                          rosoft.Network/virtualNetworkGateways/S2SConnGW"
LocalNetworkGateway2    :
Peer                    :
RoutingWeight           : 0
SharedKey               :
ConnectionStatus        : Connected
EgressBytesTransferred  : 91334484
IngressBytesTransferred : 100386089
TunnelConnectionStatus  : []
```

### Example 2: Add/Update tags to an existing VirtualNetworkGatewayConnection
```powershell
$conn = Get-AzVirtualNetworkGatewayConnection -Name 1 -ResourceGroupName myRG
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection $conn -Tag @{ testtagKey="SomeTagKey"; testtagValue="SomeKeyValue" }
```

```output
Confirm
Are you sure you want to overwrite resource '1'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y


Name                    : 1
ResourceGroupName       : myRG
Location                : westus
Id                      : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Mi
                          crosoft.Network/connections/1
Etag                    : W/"00000000-0000-0000-0000-000000000000"
ResourceGuid            : 00000000-0000-0000-0000-000000000000
ProvisioningState       : Succeeded
Tags                    :
                          Name          Value
                          ============  ============
                          testtagValue  SomeKeyValue
                          testtagKey    SomeTagKey
AuthorizationKey        :
VirtualNetworkGateway1  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/M
                          icrosoft.Network/virtualNetworkGateways/myGateway"
VirtualNetworkGateway2  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/S2SVnetConn/providers/Mic
                          rosoft.Network/virtualNetworkGateways/S2SConnGW"
LocalNetworkGateway2    :
Peer                    :
RoutingWeight           : 0
SharedKey               :
ConnectionStatus        : Connected
EgressBytesTransferred  : 91334484
IngressBytesTransferred : 100386089
TunnelConnectionStatus  : []
```

### Example 3: Add/Remove natRules to an existing VirtualNetworkGatewayConnection
```powershell
$conn = Get-AzVirtualNetworkGatewayConnection -Name 1 -ResourceGroupName myRG
$egressNatrule = Get-AzVirtualNetworkGatewayNatRule -ResourceGroupName myRG -Name "natRule1" -ParentResourceName "gw1"
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection $conn -IngressNatRule @() -EgressNatRule $egressNatrule
```

```output
Confirm
Are you sure you want to overwrite resource '1'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y


Name                    : 1
ResourceGroupName       : myRG
Location                : westus
Id                      : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Mi
                          crosoft.Network/connections/1
Etag                    : W/"00000000-0000-0000-0000-000000000000"
ResourceGuid            : 00000000-0000-0000-0000-000000000000
ProvisioningState       : Succeeded
Tags                    :
                          Name          Value
                          ============  ============
                          testtagValue  SomeKeyValue
                          testtagKey    SomeTagKey
AuthorizationKey        :
VirtualNetworkGateway1  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/M
                          icrosoft.Network/virtualNetworkGateways/myGateway"
VirtualNetworkGateway2  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/S2SVnetConn/providers/Mic
                          rosoft.Network/virtualNetworkGateways/S2SConnGW"
LocalNetworkGateway2    :
Peer                    :
RoutingWeight           : 0
SharedKey               :
ConnectionStatus        : Connected
EgressBytesTransferred  : 91334484
IngressBytesTransferred : 100386089
TunnelConnectionStatus  : []
IngressNatRules         : []
EgressNatRules          : [
                            {
                              "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Microsoft.Network/virtualNetworkGateways/gw1/natRules/natRule1"
                            }
                          ]
```

The first command gets a virtual network gateway connection named 1 that belongs to resource group myRG and stores it to the variable named $conn.
The second command gets the virtual network gateway natRule named natRule1 and stores it to the variable named $egressNatrule.
The third command sets virtual network gateway connection with removed all IngressNatRules and add egressNatrule into EgressNatRules.

### Example 3: Add/Remove GatewayCustomBgpIpAddress to an existing VirtualNetworkGatewayConnection
```powershell
$address1 = New-AzGatewayCustomBgpIpConfigurationObject -IpConfigurationId "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw/ipConfigurations/default" -CustomBgpIpAddress "169.254.21.1"
$address2 = New-AzGatewayCustomBgpIpConfigurationObject -IpConfigurationId "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw/ipConfigurations/ActiveActive" -CustomBgpIpAddress "169.254.21.3"
$conn = Get-AzVirtualNetworkGatewayConnection -ResourceGroupName PS_testing -ResourceName Conn
 
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection $conn -GatewayCustomBgpIpAddress $address1,$address2
```

```output
Name                        : Conn
ResourceGroupName           : PS_testing
Location                    : eastus
Id                          : /subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/connections/Conn
Etag                        : W/"e867e7bb-fa2e-436e-8822-70c556ec0f03"
ResourceGuid                : 9c33f4f7-b09c-4080-932e-a44405a8c252
ProvisioningState           : Succeeded
Tags                        :
AuthorizationKey            :
VirtualNetworkGateway1      : "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw"
VirtualNetworkGateway2      :
LocalNetworkGateway2        : "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/localNetworkGateways/testLng"
Peer                        :
RoutingWeight               : 3
SharedKey                   : abc
ExpressRouteGatewayBypass   : False
EnablePrivateLinkFastPath   : False
ConnectionStatus            : Unknown
EgressBytesTransferred      : 0
IngressBytesTransferred     : 0
TunnelConnectionStatus      : []
IngressNatRules             : []
EgressNatRules              : []
GatewayCustomBgpIpAddresses : [
                                {
                                  "IpconfigurationId":
                              "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw/ipConfigurations/default",
                                  "CustomBgpIpAddress": "169.254.21.1"
                                },
                                {
                                  "IpconfigurationId":
                              "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw/ipConfigurations/ActiveActive",
                                  "CustomBgpIpAddress": "169.254.21.3"
                                }
                              ]
```

This will create new AzGatewayCustomBgpIpConfigurationObjects and update gateway connection with these GatewayCustomBgpIpAddress.

### Example 4: Remove GatewayCustomBgpIpAddress to an existing VirtualNetworkGatewayConnection
```powershell
$conn = Get-AzVirtualNetworkGatewayConnection -ResourceGroupName PS_testing -ResourceName Conn
Set-AzVirtualNetworkGatewayConnection -VirtualNetworkGatewayConnection $conn -GatewayCustomBgpIpAddress @()
```

```output
Name                      : Conn
ResourceGroupName         : PS_testing
Location                  : eastus
Id                        : /subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/connections/Conn
Etag                      : W/"863d9b89-a030-42ba-9f71-58d5bc3336a9"
ResourceGuid              : 9c33f4f7-b09c-4080-932e-a44405a8c252
ProvisioningState         : Succeeded
Tags                      :
AuthorizationKey          :
VirtualNetworkGateway1    : "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/virtualNetworkGateways/testGw"
VirtualNetworkGateway2    :
LocalNetworkGateway2      : "/subscriptions/83704d68-d560-4c67-b1c7-12404db89dc3/resourceGroups/PS_testing/providers/Microsoft.Network/localNetworkGateways/testLng"
Peer                      :
RoutingWeight             : 3
SharedKey                 : abc
ExpressRouteGatewayBypass : False
EnablePrivateLinkFastPath : False
ConnectionStatus          : NotConnected
EgressBytesTransferred    : 0
IngressBytesTransferred   : 0
TunnelConnectionStatus    : []
IngressNatRules           : []
EgressNatRules            : []
GatewayCustomBgpIpAddresses : []
```

This will update gateway connection with removing these GatewayCustomBgpIpAddress.

## PARAMETERS

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

### -ConnectionMode
Virtual Network Gateway Connection Mode.

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

### -DpdTimeoutInSeconds
Dead Peer Detection Timeout of the connection in seconds.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EgressNatRule
The list of egress  NAT rules that are associated with this Connection.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSResourceId[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableBgp
Whether to use a BGP session over a S2S VPN tunnel

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

### -Force
Do not ask for confirmation if you want to overwrite a resource

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

### -GatewayCustomBgpIpAddress
The GatewayCustomBgpIpAddress of Virtual network gateway used in this connection.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSGatewayCustomBgpIpConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IngressNatRule
The list of ingress NAT rules that are associated with this Connection.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSResourceId[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpsecPolicies
A list of IPSec policies.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
A hashtable which represents resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateResourceWithTags
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficSelectorPolicy
A list of traffic selector policies.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSTrafficSelectorPolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseLocalAzureIpAddress
Whether to use PrivateIP for a S2S connection

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsePolicyBasedTrafficSelectors
Whether to use policy-based traffic selectors for a S2S connection

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkGatewayConnection
The VirtualNetworkGatewayConnection

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayConnection
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayConnection

### System.Nullable`1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.Nullable`1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy[]

### Microsoft.Azure.Commands.Network.Models.PSTrafficSelectorPolicy[]

### Microsoft.Azure.Commands.Network.Models.PSGatewayCustomBgpIpConfiguration[]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayConnection

## NOTES

## RELATED LINKS

[Get-AzVirtualNetworkGatewayConnection](./Get-AzVirtualNetworkGatewayConnection.md)

[New-AzVirtualNetworkGatewayConnection](./New-AzVirtualNetworkGatewayConnection.md)

[Remove-AzVirtualNetworkGatewayConnection](./Remove-AzVirtualNetworkGatewayConnection.md)
