---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzsOffer

## SYNOPSIS
Gets the list of public offers available for a user to subscribe. 

## SYNTAX

### TenantList (Default)
```
Get-AzsOffer [-Provider <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

### TenantGet
```
Get-AzsOffer -OfferId <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

### Admin
```
Get-AzsOffer [-Name <String>] -ResourceGroupName <String> [-Managed] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The Get-AzsOffer cmdlet gets the list of public offers available for a user to subscribe. 

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-AzsOffer -Name "ComputeOffer" -ResourceGroupName "OfferGroup" -Managed
```

Description

-----------

The example gets an offer as a service administrator

### -------------------------- EXAMPLE 2 --------------------------
```
Get-AzsOffer -Provider "default" | Where-Object name -eq "ComputeOffer"
```

Description

-----------

The example gets the list of public offers as a tenant

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

### -Managed
Managed switch specified that the operation is being executed as administrator.

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
Name of the offer.

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

### -OfferId
Specifies the id of the offer.

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

### -Provider
Specifies the Provider.
For the first party tenant scenarios this value should be "default".

```yaml
Type: String
Parameter Sets: TenantList
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name where the offer was created.

```yaml
Type: String
Parameter Sets: Admin
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

