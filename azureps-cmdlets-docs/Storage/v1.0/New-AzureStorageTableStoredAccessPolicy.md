---
external help file: RMAzure_Storage.xml
online version: a1536004-87a3-48a2-ad18-bf3fe95908c9
schema: 2.0.0
---

# New-AzureStorageTableStoredAccessPolicy
## SYNOPSIS
Creates a stored access policy for an azure_2 storage table.

## SYNTAX

```
New-AzureStorageTableStoredAccessPolicy [-Table] <String> [-Policy] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-Permission <String>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **New-AzureStorageTableStoredAccessPolicy** cmdlet creates a stored access policy for an azure_2 storage table.

## EXAMPLES

### Example 1: Create a stored access policy in a table
```
PS C:\>New-AzureStorageTableStoredAccessPolicy -Table "MyTable" -Policy "Policy02"
```

This command creates an access policy named Policy02 in the storage table named MyTable.

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

### -ExpiryTime
Specifies the time at which the stored access policy becomes invalid.

```yaml
Type: DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Permission
Specifies the level of public access to this storage table.

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

### -Policy
Specifies a stored access policy, which includes the permissions for this Shared Access Signature (SAS) token.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the time at which the stored access policy becomes valid.

```yaml
Type: DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-AzureStorageTableStoredAccessPolicy](a1536004-87a3-48a2-ad18-bf3fe95908c9)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Remove-AzureStorageTableStoredAccessPolicy](e9ed3edb-61eb-4547-8228-968601cfbee5)

[Set-AzureStorageTableStoredAccessPolicy](cd4016e4-c0aa-4963-beb7-144a5bd2d619)

