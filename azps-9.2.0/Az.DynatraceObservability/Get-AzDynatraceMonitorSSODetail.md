---
external help file: 
Module Name: Az.DynatraceObservability
online version: https://docs.microsoft.com/powershell/module/az.dynatraceobservability/get-azdynatracemonitorssodetail
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DynatraceObservability/help/Get-AzDynatraceMonitorSSODetail.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DynatraceObservability/help/Get-AzDynatraceMonitorSSODetail.md
---

# Get-AzDynatraceMonitorSSODetail

## SYNOPSIS
Gets the SSO configuration details from the partner.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.dynatraceobservability/get-azdynatracemonitorssodetail) for up-to-date information.

## SYNTAX

```
Get-AzDynatraceMonitorSSODetail -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-UserPrincipal <String>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Gets the SSO configuration details from the partner.

## EXAMPLES

### Example 1: Gets the SSO configuration details from the partner
```powershell
Get-AzDynatraceMonitorSSODetail -ResourceGroupName dyobrg -MonitorName dyob-pwsh01 -UserPrincipal "user@microsoft.com"
```

```output
AadDomain AdminUser              IsSsoEnabled MetadataUrl SingleSignOnUrl
--------- ---------              ------------ ----------- ---------------
{}        {v-diya@microsoft.com} Disabled
```

This command gets the SSO configuration details from the partner.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorName
Monitor resource name

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

### -PassThru
Returns true when the command succeeds

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

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

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

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipal
user principal id of the user

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

### Microsoft.Azure.PowerShell.Cmdlets.DynatraceObservability.Models.Api20210901.ISsoDetailsResponse

## NOTES

ALIASES

## RELATED LINKS
