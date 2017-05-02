---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRMPlan

## SYNOPSIS
Gets the details of a plan.

## SYNTAX

### TenantList (Default)
```
Get-AzureRMPlan [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### TenantGet
```
Get-AzureRMPlan -Name <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### Admin
```
Get-AzureRMPlan [-Name <String>] -ResourceGroup <String> [-Managed] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmPlan** cmdlet gets the details of a plan. This cmdlet can be executed as a service administrator or as a tenant user.

## EXAMPLES

### Example 1: Run the cmdlet as a service administrator to get the details of the specified plan
```
Get-AzureRMPlan -Name "ComputePlan" -ResourceGroup "PlanGroup" -Managed
```

This example gets the details of the plan named "ComputePlan" and created in the resource group "PlanGroup".
The presence of the **Managed** parameter runs the cmdlet as a service administrator.

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

### -Managed
Indicates whether the operation is being executed as a service administrator.

```yaml
Type: SwitchParameter
Parameter Sets: Admin
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the plan.

```yaml
Type: String
Parameter Sets: TenantGet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Admin
Aliases:

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

### -ResourceGroup
Specifies name of the resource group where the plan was created.

```yaml
Type: String
Parameter Sets: Admin
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
