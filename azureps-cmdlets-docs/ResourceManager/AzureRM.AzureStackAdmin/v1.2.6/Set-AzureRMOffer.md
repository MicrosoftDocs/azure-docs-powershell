---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F55E508B-A369-41E0-9928-2507BCB9617B
---

# Set-AzureRMOffer

## SYNOPSIS
The Set-AzureRmOffer cmdlet updates the existing offer

## SYNTAX

```
Set-AzureRMOffer -Offer <AdminOfferModel> -ResourceGroup <String> [-SubscriptionId <Guid>] [-AdminUri <Uri>]
 [-Token <String>] [-ApiVersion <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The Set-AzureRmOffer cmdlet updates the existing offer

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$Offer = Get-AzureRMOffer -Name "ComputeOffer" -ResourceGroup "OfferGroup" -Managed; $Offer.DisplayName ="New Compute Offer";  Set-AzureRMOffer -Plan $Offer -ResourceGroup "OfferGroup"
```

Description

-----------

The example gets and updates the offer name 'ComputeOffer'

## PARAMETERS

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in future

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiVersion
Specifies the api version supported.
This is optional.
This parameter will be deprecated in future

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Not Specified

The following values are permitted for this object type.

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
Not Specified

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
@{Text=}

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
Not Specified

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
Specifies the resource group name of the offer

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
Service administrator subscription id.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

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

### -Token
Authentication token for making the request.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Models.AdminOfferModel

## NOTES
## RELATED LINKS

