---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/update-azvpngatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVpnGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVpnGatewayNatRule.md
---

# Update-AzVpnGatewayNatRule

## SYNOPSIS
Updates a NAT rule associated with VpnGateway.

## SYNTAX

### ByVpnGatewayNatRuleName (Default)
```
Update-AzVpnGatewayNatRule -ResourceGroupName <String> -ParentResourceName <String> -Name <String>
 [-Type <String>] [-Mode <String>] [-InternalMapping <String[]>] [-ExternalMapping <String[]>]
 [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByVpnGatewayNatRuleResourceId
```
Update-AzVpnGatewayNatRule -ResourceId <String> [-Type <String>] [-Mode <String>] [-InternalMapping <String[]>]
 [-ExternalMapping <String[]>] [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>]
 [-IpConfigurationId <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVpnGatewayNatRuleObject
```
Update-AzVpnGatewayNatRule -InputObject <PSVpnGatewayNatRule> [-Type <String>] [-Mode <String>]
 [-InternalMapping <String[]>] [-ExternalMapping <String[]>] [-InternalPortRange <String[]>]
 [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzVpnGatewayNatRule** cmdlet updates a NAT rule associated with VpnGateway.

## EXAMPLES

### Example

```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$virtualWan = New-AzVirtualWan -ResourceGroupName testRG -Name myVirtualWAN -Location "West US"
$virtualHub = New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.0.1/24"
New-AzVpnGateway -ResourceGroupName "testRG" -Name "testvpngw" -VirtualHubId $virtualHub.Id -VpnGatewayScaleUnit 2
$vpnGateway = Get-AzVpnGateway -ResourceGroupName "testRG" -Name "testvpngw"
New-AzVpnGatewayNatRule -ResourceGroupName $vpnGateway.ResourceGroupName -ParentResourceName $vpnGateway.Name -Name "testNatRule" -Type Static -Mode EgressSnat -InternalMapping "10.0.0.1/26" -ExternalMapping "192.168.0.0/26"
$natRule = Get-AzVpnGatewayNatRule -ResourceGroupName $vpnGateway.ResourceGroupName -ParentResourceName $vpnGateway.Name -Name "testNatRule"
Update-AzVpnGatewayNatRule -InputObject $natRule -Type Dynamic -Mode IngressSnat
```

```output
Type                      : Dynamic
Mode                      : IngressSnat
VpnConnectionProtocolType : IKEv2
InternalMappings          : 10.0.0.1/26
ExternalMappings          : 192.168.0.0/26
IpConfigurationId         :
IngressVpnSiteLinkConnections : [Microsoft.Azure.Commands.Network.Models.PSResourceId]
EgressVpnSiteLinkConnections  : [Microsoft.Azure.Commands.Network.Models.PSResourceId]
ProvisioningState         : Provisioned
Name                      : ps9709
Etag                      : W/"4580a2e2-2fab-4cff-88eb-92013a76b5a8"
Id                        : /subscriptions/{subscriptionId}/resourceGroups/testRg/providers/Microsoft.Network/vpnGateways/testvpngw/natRules/testNatRule
```

The above will create a resource group, Virtual WAN, Virtual Network, Virtual Hub. Then, we will create VpnGateway under that Virtual Hub. Then, create new NAT rule associated with created VpnGateway.
Using this command: Update-AzVpnGatewayNatRule, update NAT rule.

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

### -ExternalMapping
The list of private IP address subnet external mappings for NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPortRange
The list of external port range mappings for NAT subnets

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
The VpnGatewayNatRule object to update.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule
Parameter Sets: ByVpnGatewayNatRuleObject
Aliases: VpnGatewayNatRule

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternalMapping
The list of private IP address subnet internal mappings for NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalPortRange
The list of internal port range mappings for NAT subnets

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpConfigurationId
The IP Configuration ID this NAT rule applies to

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

### -Mode
The Source NAT direction of a VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: EgressSnat, IngressSnat

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
Parameter Sets: ByVpnGatewayNatRuleName
Aliases: ResourceName, VpnGatewayNatRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentResourceName
The parent resource name.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleName
Aliases: ParentVpnGatewayName, VpnGatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
The resource id of the VpnGatewayNatRule object to delete.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleResourceId
Aliases: VpnGatewayNatRuleResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
The type of NAT rule for VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Static, Dynamic

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

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule

## NOTES

## RELATED LINKS
