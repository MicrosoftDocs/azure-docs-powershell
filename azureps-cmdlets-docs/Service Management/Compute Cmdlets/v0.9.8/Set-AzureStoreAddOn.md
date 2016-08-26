---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Set-AzureStoreAddOn
## SYNOPSIS
Updates an existing add-on instance.

## SYNTAX

```
Set-AzureStoreAddOn [-Name] <String> [-Plan] <String> [[-PromotionCode] <String>] [-PassThru]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

This cmdlet updates an existing add-on instance from the current subscription.

## EXAMPLES

### Example 1
```
PS C:\>Set-AzureStoreAddOn MyAddOn NewPlanId
```

This example updates an add-on with a new plan ID.

### Example 2
```
PS C:\>Set-AzureStoreAddOn MyAddOn NewPlanId MyPromoCode
```

This example updates an add-on with a new plan ID and promotional code.

## PARAMETERS

### -Name
Specifies the name of the add-on instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
If specified, the cmdlet returns true if the command succeeds and false if it fails.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: 
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
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromotionCode
Specifies the promotional code.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStoreAddOn](ceb557b5-e9af-4797-8385-94078de84662)

[New-AzureStoreAddOn](a293ef75-d822-4392-8af4-1bb50d0461f6)

[Remove-AzureStoreAddOn](38bb8f09-dcc3-4356-b346-354dd186feca)

