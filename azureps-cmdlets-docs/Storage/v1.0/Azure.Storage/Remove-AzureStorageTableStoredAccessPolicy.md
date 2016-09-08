---
external help file: RMAzure_Storage.xml
online version: a1536004-87a3-48a2-ad18-bf3fe95908c9
schema: 2.0.0
---

# Remove-AzureStorageTableStoredAccessPolicy
## SYNOPSIS
Removes a stored access policy from an azure_2 storage table.

## SYNTAX

```
Remove-AzureStorageTableStoredAccessPolicy [-Table] <String> [-Policy] <String>
 [-Context <AzureStorageContext>] [-Force] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageTableStoredAccessPolicy** cmdlet removes a stored access policy from an azure_2 storage table.

## EXAMPLES

### Example 1: Remove a stored access policy from a storage table
```
PS C:\>Remove-AzureStorageTableStoredAccessPolicy -Table "MyTable" -Policy "Policy05"
```

This command removes policy named Policy05 from storage table named MyTable.

## PARAMETERS

### -Context
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Force
ps_force

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

### -PassThru
Indicates that this cmdlet returns a **Boolean** that reflects the success of the operation.
By default, this cmdlet does not return a value.

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

### -Policy
Specifies the stored access policy, which includes the permissions for this SAS token.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Table
Specifies the azure_2 table name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 1
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

[Get-AzureStorageTableStoredAccessPolicy](a1536004-87a3-48a2-ad18-bf3fe95908c9)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[New-AzureStorageTableStoredAccessPolicy](27f043ca-0c6b-4952-afd7-a2e12e73b402)

[Set-AzureStorageTableStoredAccessPolicy](cd4016e4-c0aa-4963-beb7-144a5bd2d619)

