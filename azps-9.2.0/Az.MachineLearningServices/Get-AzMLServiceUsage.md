---
external help file: 
Module Name: Az.MachineLearningServices
online version: https://docs.microsoft.com/powershell/module/az.machinelearningservices/get-azmlserviceusage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/Get-AzMLServiceUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/Get-AzMLServiceUsage.md
---

# Get-AzMLServiceUsage

## SYNOPSIS
Gets the current usage information as well as limits for AML resources for given subscription and location.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.machinelearningservices/get-azmlserviceusage) for up-to-date information.

## SYNTAX

```
Get-AzMLServiceUsage -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets the current usage information as well as limits for AML resources for given subscription and location.

## EXAMPLES

### Example 1: Gets the current usage information as well as limits for AML resources for given subscription and location
```powershell
Get-AzMLServiceUsage -Location eastus
```

```output
AmlWorkspaceLocation CurrentValue Limit Unit
-------------------- ------------ ----- ----
                     9            200   Count
                     8            100   Count
                     0            100   Count
```

Gets the current usage information as well as limits for AML resources for given subscription and location.

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

### -Location
The location for which resource usage is queried.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Models.Api20220501.IUsage

## NOTES

ALIASES

## RELATED LINKS
