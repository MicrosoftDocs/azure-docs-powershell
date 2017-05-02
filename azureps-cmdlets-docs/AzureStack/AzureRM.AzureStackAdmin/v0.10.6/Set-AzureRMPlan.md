---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMPlan

## SYNOPSIS
Updates the existing plan with the given modified plan object.

## SYNTAX

```
Set-AzureRMPlan -Plan <AdminPlanModel> -ResourceGroup <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRMPlan** cmdlet updates the existing plan with the given modified plan object.

## EXAMPLES

### Example 1: Change a property of an existing plan
```
$planToUpdate = Get-AzureRMPlan -Name "ComputePlan" -ResourceGroup "PlanGroup" -Managed
$planToUpdate.DisplayName = "Plan A"
Set-AzureRMPlan -Plan $planToUpdate -ResourceGroup "PlanGroup"
```

This example modifies the **DisplayName** property of the plan named "ComputePlan" in the "PlanGroup" resource group.
The first statement gets the plan and stores the object in the $planToUpdate variable.
After the **DisplayName** property of the plan is changed, the updated object is passed in the **Plan** parameter of the **Set-AzureRMPlan** cmdlet.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies a variable that is used for storing an informational message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Specifies a variable that stores the value of the current pipeline element.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Plan
Specifies an updated **AdminPlanModel** object to be used for updating the existing plan data.

```yaml
Type: AdminPlanModel
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the name of the resource group of the plan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.AdminPlanModel

## NOTES

## RELATED LINKS
