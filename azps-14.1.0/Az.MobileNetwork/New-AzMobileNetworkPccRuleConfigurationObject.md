---
external help file: Az.MobileNetwork-help.xml
Module Name: Az.MobileNetwork
online version: https://learn.microsoft.com/powershell/module/Az.MobileNetwork/new-azmobilenetworkpccruleconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/New-AzMobileNetworkPccRuleConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/New-AzMobileNetworkPccRuleConfigurationObject.md
---

# New-AzMobileNetworkPccRuleConfigurationObject

## SYNOPSIS
Create an in-memory object for PccRuleConfiguration.

## SYNTAX

```
New-AzMobileNetworkPccRuleConfigurationObject -RuleName <String> -RulePrecedence <Int32>
 -ServiceDataFlowTemplate <IServiceDataFlowTemplate[]> [-GuaranteedBitRateDownlink <String>]
 [-GuaranteedBitRateUplink <String>] [-RuleQoPolicyAllocationAndRetentionPriorityLevel <Int32>]
 [-RuleQoPolicyFiveQi <Int32>] [-RuleQoPolicyMaximumBitRateDownlink <String>]
 [-RuleQoPolicyMaximumBitRateUplink <String>] [-RuleQoPolicyPreemptionCapability <String>]
 [-RuleQoPolicyPreemptionVulnerability <String>] [-TrafficControl <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for PccRuleConfiguration.

## EXAMPLES

### Example 1: Create an in-memory object for PccRuleConfiguration.
```powershell
$ServiceDataFlowTemplate = New-AzMobileNetworkServiceDataFlowTemplateObject -Direction "Bidirectional" -Protocol "255" -RemoteIPList "any" -TemplateName azps-mn-flow-template

New-AzMobileNetworkPccRuleConfigurationObject -RuleName azps-mn-service-rule -RulePrecedence 0 -ServiceDataFlowTemplate $ServiceDataFlowTemplate -TrafficControl 'Enabled' -RuleQoPolicyPreemptionVulnerability 'Preemptable' -RuleQoPolicyPreemptionCapability 'NotPreempt' -RuleQoPolicyAllocationAndRetentionPriorityLevel 9 -RuleQoPolicyMaximumBitRateDownlink "1 Gbps" -RuleQoPolicyMaximumBitRateUplink "500 Mbps"
```

```output
RuleName             RulePrecedence TrafficControl
--------             -------------- --------------
azps-mn-service-rule 0              Enabled
```

Create an in-memory object for PccRuleConfiguration.

## PARAMETERS

### -GuaranteedBitRateDownlink
Downlink bit rate.

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

### -GuaranteedBitRateUplink
Uplink bit rate.

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

### -RuleName
The name of the rule.
This must be unique within the parent service.
You must not use any of the following reserved strings - 'default', 'requested' or 'service'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RulePrecedence
A precedence value that is used to decide between data flow policy rules when identifying the QoS values to use for a particular SIM.
A lower value means a higher priority.
This value should be unique among all data flow policy rules configured in the mobile network.

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

### -RuleQoPolicyAllocationAndRetentionPriorityLevel
QoS Flow allocation and retention priority (ARP) level.
Flows with higher priority preempt flows with lower priority, if the settings of preemptionCapability and preemptionVulnerability allow it.
1 is the highest level of priority.
If this field is not specified then 5qi is used to derive the ARP value.
See 3GPP TS23.501 section 5.7.2.2 for a full description of the ARP parameters.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleQoPolicyFiveQi
5G QoS Flow Indicator value.
The 5QI identifies a specific QoS forwarding treatment to be provided to a flow.
See 3GPP TS23.501 section 5.7.2.1 for a full description of the 5QI parameter, and table 5.7.4-1 for the definition the 5QI values.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleQoPolicyMaximumBitRateDownlink
Downlink bit rate.

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

### -RuleQoPolicyMaximumBitRateUplink
Uplink bit rate.

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

### -RuleQoPolicyPreemptionCapability
QoS Flow preemption capability.
The preemption capability of a QoS Flow controls whether it can preempt another QoS Flow with a lower priority level.
See 3GPP TS23.501 section 5.7.2.2 for a full description of the ARP parameters.

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

### -RuleQoPolicyPreemptionVulnerability
QoS Flow preemption vulnerability.
The preemption vulnerability of a QoS Flow controls whether it can be preempted by a QoS Flow with a higher priority level.
See 3GPP TS23.501 section 5.7.2.2 for a full description of the ARP parameters.

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

### -ServiceDataFlowTemplate
The set of data flow templates to use for this data flow policy rule.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IServiceDataFlowTemplate[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficControl
Determines whether flows that match this data flow policy rule are permitted.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.PccRuleConfiguration

## NOTES

## RELATED LINKS
