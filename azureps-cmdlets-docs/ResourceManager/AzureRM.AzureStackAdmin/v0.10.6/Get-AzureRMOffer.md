---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRMOffer

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### TenantList (Default)
```
Get-AzureRMOffer [-Provider <String>] [<CommonParameters>]
```

### TenantGet
```
Get-AzureRMOffer -OfferId <String> [<CommonParameters>]
```

### Admin
```
Get-AzureRMOffer [-Name <String>] -ResourceGroup <String> [-Managed] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Managed
{{Fill Managed Description}}

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
{{Fill Name Description}}

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
{{Fill OfferId Description}}

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

### -Provider
{{Fill Provider Description}}

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
{{Fill ResourceGroup Description}}

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
Microsoft.AzureStack.Management.Models.AdminOfferModel

## NOTES

## RELATED LINKS

