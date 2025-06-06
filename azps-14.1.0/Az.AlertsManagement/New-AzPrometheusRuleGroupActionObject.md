---
external help file: Az.PrometheusRuleGroups.psm1-help.xml
Module Name: Az.AlertsManagement
online version: https://learn.microsoft.com/powershell/module/Az.AlertsManagement/new-azprometheusrulegroupactionobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/New-AzPrometheusRuleGroupActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/New-AzPrometheusRuleGroupActionObject.md
---

# New-AzPrometheusRuleGroupActionObject

## SYNOPSIS
Create an in-memory object for PrometheusRuleGroupAction.

## SYNTAX

```
New-AzPrometheusRuleGroupActionObject [-ActionGroupId <String>]
 [-ActionProperty <IPrometheusRuleGroupActionProperties>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for PrometheusRuleGroupAction.

## EXAMPLES

### Example 1: Create an in-memory object for PrometheusRuleGroupAction.
```powershell
New-AzPrometheusRuleGroupActionObject -ActionGroupId /subscriptions/fffffffff-ffff-ffff-ffff-ffffffffffff/resourceGroups/MyresourceGroup/providers/microsoft.insights/actiongroups/MyActionGroup -ActionProperty @{"key1" = "value1"}
```

```output
ActionGroupId
-------------
/subscriptions/fffffffff-ffff-ffff-ffff-ffffffffffff/resourceGroups/MyresourceGroup/providers/microsoft.insights/acti…
```

Create an in-memory object for PrometheusRuleGroupAction.

## PARAMETERS

### -ActionGroupId
The resource id of the action group to use.

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

### -ActionProperty
The properties of an action group object.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.PrometheusRuleGroups.Models.IPrometheusRuleGroupActionProperties
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

### Microsoft.Azure.PowerShell.Cmdlets.PrometheusRuleGroups.Models.PrometheusRuleGroupAction

## NOTES

## RELATED LINKS
