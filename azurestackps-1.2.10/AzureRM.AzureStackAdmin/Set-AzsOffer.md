---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Set-AzsOffer

## SYNOPSIS
Updates an existing offer.

## SYNTAX

```
Set-AzsOffer -Offer <AdminOfferModel> -ResourceGroupName <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Set-AzsOffer cmdlet updates the existing offer.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$Offer = Get-AzsOffer -Name "ComputeOffer" -ResourceGroupName "OfferGroup" -Managed; $Offer.DisplayName ="New Compute Offer";  Set-AzsOffer -Plan $Offer -ResourceGroupName "OfferGroup"
```

Description

-----------

The example gets and updates the offer name 'ComputeOffer'.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event. The following values are permitted for this object type.

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

### -Offer
Specifies an updated AdminOfferModel object to be used for updating the existing offer data.

```yaml
Type: AdminOfferModel
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ResourceGroupName
Specifies the resource group name of the offer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceGroup

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


