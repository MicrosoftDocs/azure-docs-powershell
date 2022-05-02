---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azfirewallpolicyintrusiondetectionsignatureoverride
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicyIntrusionDetectionSignatureOverride.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicyIntrusionDetectionSignatureOverride.md
---

# New-AzFirewallPolicyIntrusionDetectionSignatureOverride

## SYNOPSIS
Creates a new Azure Firewall Policy Intrusion Detection Signature Override

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.network/new-azfirewallpolicyintrusiondetectionsignatureoverride) for up-to-date information.

## SYNTAX

```
New-AzFirewallPolicyIntrusionDetectionSignatureOverride -Id <UInt64> -Mode <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzFirewallPolicyIntrusionDetectionSignatureOverride** cmdlet creates an Azure Firewall Policy Signature Override Object.

## EXAMPLES

### Example 1: Create intrusion detection with signature overrides
```powershell
$signatureOverride = New-AzFirewallPolicyIntrusionDetectionSignatureOverride -Id "123456798" -Mode "Deny"
New-AzFirewallPolicyIntrusionDetection -Mode "Alert" -SignatureOverride $signatureOverride
```
This example creates intrusion detection with specific signature override to Deny mode

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Signature id.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Signature state.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Off, Alert, Deny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
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

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicyIntrusionDetectionSignatureOverride

## NOTES

## RELATED LINKS