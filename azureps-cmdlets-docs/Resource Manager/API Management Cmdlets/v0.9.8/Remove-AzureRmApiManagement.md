---
external help file: RMAzure_Apimanagement.xml
online version: b3b67164-7adf-4fe3-87ab-51dcd46ed084
schema: 2.0.0
---

# Remove-AzureRmApiManagement
## SYNOPSIS
Removes an API Management service.

## SYNTAX

```
Remove-AzureRmApiManagement [-PassThru] -Name <String> -ResourceGroupName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmApiManagement** cmdlet removes an azure_2 API Management service.

## EXAMPLES

### Example 1: Remove an API Management service
```
PS C:\>Remove-AzureRmApiManagement -ResourceGroupName "ContosoGroup02" -Name "ContosoApi"
```

This command removes the API Management service named ContosoApi.

## PARAMETERS

### -Name
Specifies the name of the API Management deployment that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a value of $True if the operation succeeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the of resource group under which the API Management deployment exists.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](b3b67164-7adf-4fe3-87ab-51dcd46ed084)

[Get-AzureRmApiManagement](e067ded3-a2e3-4d53-8628-0ebbafa62721)

[New-AzureRmApiManagement](6b5595ca-246e-4381-a37e-24dfae307109)

[Restore-AzureRmApiManagement](b0ff412d-269a-472f-8d79-9c0b9f0ebac2)

