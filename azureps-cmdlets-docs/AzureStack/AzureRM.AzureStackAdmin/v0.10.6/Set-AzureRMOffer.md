---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMOffer

## SYNOPSIS
Updates an existing offer.

## SYNTAX

```
Set-AzureRMOffer -Offer <AdminOfferModel> -ResourceGroup <String> [-SubscriptionId <Guid>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmOffer** cmdlet updates an existing offer.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$offerUpdated = Get-AzureRMOffer -Name "ComputeOffer" -ResourceGroup "OfferGroup" -Managed
$offerUpdated.DisplayName ="New Compute Offer"
Set-AzureRMOffer -Offer $offerUpdated -ResourceGroup "OfferGroup"
```

This example gets and updates the offer named "ComputeOffer" that belongs to the "OfferGroup" resource group.

## PARAMETERS

### -InformationAction
Not specified.

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
Not specified.

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
Specifies an updated **AdminOfferModel** object to be used for updating the existing offer data.

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
Not specified.

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
Specifies the name of the resource group that contains the offer.

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

### -SubscriptionId
Specifies the subscription ID of the service administrator. This parameter is not needed when you use the cmdlet in the Azure stack environment configured against Azure Active Directory.

```yaml
Type: Guid
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
