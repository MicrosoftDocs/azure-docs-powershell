---
external help file: RMAzure_Storage.xml
online version: 27f043ca-0c6b-4952-afd7-a2e12e73b402
schema: 2.0.0
---

# Get-AzureStorageTableStoredAccessPolicy
## SYNOPSIS
Gets the stored access policy or policies for an azure_2 storage table.

## SYNTAX

```
Get-AzureStorageTableStoredAccessPolicy [-Table] <String> [[-Policy] <String>] [-Context <AzureStorageContext>]
```

## DESCRIPTION
The **Get-AzureStorageTableStoredAccessPolicy** cmdlet lists the stored access policy or policies for an azure_2 storage table.

## EXAMPLES

### Example 1: Get a stored access policy in a storage table
```
PS C:\>Get-AzureStorageTableStoredAccessPolicy -Table "Table02" -Policy "Policy50"
```

This command gets the access policy named Policy50 in the storage table named Table02.

### Example 2: Get all stored access policies in a storage table
```
PS C:\>Get-AzureStorageTableStoredAccessPolicy -Table "Table02"
```

This command gets all access policies in the table named Table02.

## PARAMETERS

### -Context
Specifies the azure_2 storage context.
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

### -Policy
Specifies a stored access policy, which includes the permissions for this Shared Access Signature (SAS) token.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Table
Specifies the azure_2 storage table name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageTableStoredAccessPolicy](27f043ca-0c6b-4952-afd7-a2e12e73b402)

[Remove-AzureStorageTableStoredAccessPolicy](e9ed3edb-61eb-4547-8228-968601cfbee5)

[Set-AzureStorageTableStoredAccessPolicy](cd4016e4-c0aa-4963-beb7-144a5bd2d619)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

