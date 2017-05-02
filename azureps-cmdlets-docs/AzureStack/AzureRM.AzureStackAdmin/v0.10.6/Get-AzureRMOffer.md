---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRMOffer

## SYNOPSIS
Gets an offer as an administrator or as a tenant user.

## SYNTAX

### TenantList (Default)
```
Get-AzureRMOffer [-Provider <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### TenantGet
```
Get-AzureRMOffer -OfferId <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### Admin
```
Get-AzureRMOffer [-Name <String>] -ResourceGroup <String> [-Managed] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRMOffer** cmdlet gets an offer. This cmdlet can be executed as a service administrator or as a tenant user.

## EXAMPLES

### Example 1: Run the cmdlet as a service administrator to get the specified offer
```
Get-AzureRMOffer -Name "ComputeOffer" -ResourceGroup "OfferGroup" -Managed
```

This example gets the offer named "ComputeOffer" and created in the "OfferGroup" resource group. The presence of the **Managed** parameter runs the cmdlet as a service administrator.

### Example 2: Run the cmdlet as a tenant user to get a list of offers
```
Get-AzureRMOffer -Provider "default" | Where-Object name -eq "ComputeOffer"
```

This example gets a list of public offers and then pipes the list to the **Where-Object** cmdlet to filter out all offers except the ones named "ComputeOffer".

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
Specifies the name of the offer.

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
Specifies the ID of the offer.

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
Specifies the Provider. For the first party tenant scenarios this value should be "default".

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

### -ResourceGroup
Specifies the name of the resource group where the offer was created.

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

### Microsoft.AzureStack.Management.Models.OfferDefinition
### Microsoft.AzureStack.Management.Models.AdminOfferModel

## NOTES

## RELATED LINKS
