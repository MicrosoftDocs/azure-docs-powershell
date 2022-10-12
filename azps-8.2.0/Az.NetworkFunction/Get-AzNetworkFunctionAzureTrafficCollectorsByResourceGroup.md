---
external help file: 
Module Name: Az.NetworkFunction
online version: https://docs.microsoft.com/powershell/module/az.networkfunction/get-aznetworkfunctionazuretrafficcollectorsbyresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetworkFunction/help/Get-AzNetworkFunctionAzureTrafficCollectorsByResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetworkFunction/help/Get-AzNetworkFunctionAzureTrafficCollectorsByResourceGroup.md
---

# Get-AzNetworkFunctionAzureTrafficCollectorsByResourceGroup

## SYNOPSIS
Return list of Azure Traffic Collectors in a Resource Group

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.networkfunction/get-aznetworkfunctionazuretrafficcollectorsbyresourcegroup) for up-to-date information.

## SYNTAX

```
Get-AzNetworkFunctionAzureTrafficCollectorsByResourceGroup -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Return list of Azure Traffic Collectors in a Resource Group

## EXAMPLES

### Example 1: {{ Add title here }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Add description here }}

### Example 2: {{ Add title here }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Add description here }}

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

### -ResourceGroupName
The name of the resource group.

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
Azure Subscription ID.

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

### Microsoft.Azure.PowerShell.Cmdlets.NetworkFunction.Models.Api20220501.IAzureTrafficCollector

## NOTES

ALIASES

## RELATED LINKS

