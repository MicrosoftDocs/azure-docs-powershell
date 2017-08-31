---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzsManagedOffer

## SYNOPSIS
The Get-AzsManagedOffer cmdlet  lists the private and public offers created by an administrator. 

## SYNTAX

```
Get-AzsManagedOffer [-Name <String>] -ResourceGroupName <String>
```

## DESCRIPTION
The Get-AzsManagedOffer cmdlet lists the private and public offers created by an administrator. 

## EXAMPLES

### Example 1
```
Get-AzsManagedOffer
```

## PARAMETERS

### -Name
Name of the offer

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

### -ResourceGroupName
Resource group which contains the offer.

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

