---
external help file: Az.NetworkFunction-help.xml
Module Name: Az.NetworkFunction
online version: https://learn.microsoft.com/powershell/module/az.networkfunction/update-aznetworkfunctiontrafficcollector
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetworkFunction/NetworkFunction/help/Update-AzNetworkFunctionTrafficCollector.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetworkFunction/NetworkFunction/help/Update-AzNetworkFunctionTrafficCollector.md
---

# Update-AzNetworkFunctionTrafficCollector

## SYNOPSIS
Creates or updates a Azure Traffic Collector resource

## SYNTAX

```
Update-AzNetworkFunctionTrafficCollector -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 -Location <String> [-CollectorPolicy <ICollectorPolicy[]>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Creates or updates a Azure Traffic Collector resource

## EXAMPLES

### Example 1: Updates a traffic collector
```powershell
Update-AzNetworkFunctionTrafficCollector -name atctestps -resourcegroupname test -location eastus | Format-List
```

```output
CollectorPolicies : {}
Etag              : cf0336a2-7454-4aa4-add9-1de3e2291143
Id                : /subscriptions/62364504-2406-418e-971c-05822ff72fad/resourceGroups/test/providers/Microsoft.NetworkFunction/azureTrafficCollectors/atctestps
Location          : eastus
Name              : atctestps
ProvisioningState : Succeeded
Tags              : Microsoft.Azure.PowerShell.Cmdlets.AzureTrafficCollector.Models.ResourceTags
Type              : Microsoft.NetworkFunction/AzureTrafficCollectors
```

This cmdlet updates a traffic collector.

## PARAMETERS

### -AsJob
Run the command as a job

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

### -CollectorPolicy
Collector Policies for Azure Traffic Collector.
To construct, see NOTES section for COLLECTORPOLICY properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.NetworkFunction.Models.ICollectorPolicy[]
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
Resource location.

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

### -Name
Azure Traffic Collector name

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AzureTrafficCollectorName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Resource tags.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.NetworkFunction.Models.IAzureTrafficCollector

## NOTES

## RELATED LINKS
