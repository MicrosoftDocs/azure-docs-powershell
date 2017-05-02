---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRMOffer

## SYNOPSIS
Creates an offer comprising the specified base plans and add-on plans.

## SYNTAX

```
New-AzureRMOffer -Name <String> [-DisplayName <String>] [-State <AccessibilityState>]
 [-AddOnPlans <AddonPlanDefinition[]>] [-BasePlanIds <String[]>] -ArmLocation <String> -ResourceGroup <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmOffer** cmdlet creates an offer comprising the specified base plans and add-on plans.

## EXAMPLES

### Example 1: Create an offer
```
New-AzureRMOffer -Name "ComputePlan" -DisplayName "ComputePlan" -State Private -BasePlanIds $BasePlanIds -ArmLocation "local" -ResourceGroup "OfferGroup"
```

This example creates an offer with the base plans specified by $BasePlanIds.

## PARAMETERS

### -AddOnPlans
Specifies an array of add-on plan IDs. The offer will support the extra quotas that are provided by the add-on plans.

```yaml
Type: AddonPlanDefinition[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ArmLocation
Specifies the location of the Azure stack resource manager in the Azure stack installation.

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

### -BasePlanIds
Specifies an array of base plan IDs. The offer comprises all the base plans and associated quotas.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the offer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Name
Specifies the name of the offer.

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
Specifies the name of the resource group where the offer resource is created.

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

### -State
Specifies the state of the offer plan. The acceptable values for this parameter are:
- Private
- Public
- Decommissioned

```yaml
Type: AccessibilityState
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.AzureStack.Management.Models.AdminOfferModel

## NOTES

## RELATED LINKS
