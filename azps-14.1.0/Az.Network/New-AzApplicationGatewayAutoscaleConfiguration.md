---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/new-azapplicationgatewayautoscaleconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayAutoscaleConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayAutoscaleConfiguration.md
---

# New-AzApplicationGatewayAutoscaleConfiguration

## SYNOPSIS
Creates a Autoscale Configuration for the Application Gateway.

## SYNTAX

```
New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity <Int32> [-MaxCapacity <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzApplicationGatewayAutoscaleConfiguration** cmdlet creates Autoscale Configuration for an Azure application gateway.

## EXAMPLES

### Example 1
```powershell
$AutoscaleConfig = New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity 3
$Gateway = New-AzApplicationGateway -Name "AppGateway01" -ResourceGroupName "ResourceGroup01" -Location "West US" -BackendAddressPools $Pool -BackendHttpSettingsCollection $PoolSetting -FrontendIpConfigurations $FrontEndIpConfig -GatewayIpConfigurations $GatewayIpConfig -FrontendPorts $FrontEndPort -HttpListeners $Listener -RequestRoutingRules $Rule -Sku $Sku -AutoscaleConfiguration $AutoscaleConfig
```

The first command creates an autoscale configuration with minimum capacity 3.
The second command creates an application gateway with the autoscale configuration.

### Example 2

```powershell
$gw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$gw.Sku.Capacity = $null
$gw.AutoscaleConfiguration = New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity 2 -MaxCapacity 4
$gw = Set-AzApplicationGateway -ApplicationGateway $gw
```

The first command gets the configuration of the Application Gateway into a variable.
The second command clears the SKU Capacity variable to allow the Autoscale Configuration to be set.
The third command specifies a new AutoScale Configuration for the Application Gateway.
The fourth command applies the new configuration to the Application Gateway.

## PARAMETERS

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

### -MaxCapacity
Maximum capacity units that will always be available [and charged] for application gateway.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinCapacity
Minimum capacity units that will always be available [and charged] for application gateway. 

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
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

### None

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAutoscaleConfiguration

## NOTES

## RELATED LINKS

[Get-AzApplicationGatewayAutoscaleConfiguration](./Get-AzApplicationGatewayAutoscaleConfiguration.md)

[Remove-AzApplicationGatewayAutoscaleConfiguration](./Remove-AzApplicationGatewayAutoscaleConfiguration.md)

[Set-AzApplicationGatewayAutoscaleConfiguration](./Set-AzApplicationGatewayAutoscaleConfiguration.md)
