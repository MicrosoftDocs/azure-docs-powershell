---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureStoreAddOn

## SYNOPSIS
Buys a new add-on instance.

## SYNTAX

```
New-AzureStoreAddOn [-Name] <String> [-AddOn] <String> [-Plan] <String> [-Location] <String>
 [[-PromotionCode] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

Buys a new add-on instance from the Azure Store.

## EXAMPLES

### Example 1
```
PS C:\>New-AzureStoreAddOn MyAddOn AddonId PlanId "West US"
```

This example buys an add-on named MyAddOn with a PlanId in West US location.

### Example 2
```
PS C:\>New-AzureStoreAddOn MyAddOn AddonId PlanId "West US" MyPromoCode
```

This example uses a promotional code to buy an add-on.

## PARAMETERS

### -Name
Specifies the name of the add-on instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Plan
Specifies the plan ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the add-on instance location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromotionCode
Specifies a promotion code to apply to the purchase.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddOn
Specifies the add-on ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStoreAddOn](.\Get-AzureStoreAddOn.md)

[Remove-AzureStoreAddOn](.\Remove-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](.\Set-AzureStoreAddOn.md)

