---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRMOffer

## SYNOPSIS
Gets an offer.

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

### Example 1:
```
Get-AzureRMOffer -Name "ComputeOffer" -ResourceGroup "OfferGroup" -Managed
```

This command gets the offer named "ComputeOffer" and created in the "OfferGroup" resource group. This command is being executed as a service administrator.

### Example 2:
```
Get-AzureRMOffer -Provider "default" | Where-Object name -eq "ComputeOffer"
```

This command gets the list of public offers. The command is being executed as a tenant user.

## PARAMETERS

### -InformationAction
Not Specified.

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
Not Specified.

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
Not Specified.

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
