---
external help file: RMAzure_Storage.xml
online version: 36ff9a70-74d8-4b37-9962-c01b531c9a01
schema: 2.0.0
---

# Get-AzureStorageTable
## SYNOPSIS
Lists the storage tables.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageTable [[-Name] <String>] [-Context <AzureStorageContext>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageTable [-Context <AzureStorageContext>] -Prefix <String>
```

## DESCRIPTION
The **Get-AzureStorageTable** cmdlet lists the storage tables associated with the storage account in azure_2.

## EXAMPLES

### Example 1: List all Azure Storage tables
```
PS C:\>Get-AzureStorageTable
```

This command gets all storage tables for a Storage account.

### Example 2: List Azure Storage tables using a wildcard character
```
PS C:\>Get-AzureStorageTable -Name table*
```

This command uses a wildcard character to get storage tables whose name starts with table.

### Example 3: List Azure Storage tables using table name prefix
```
PS C:\>Get-AzureStorageTable -Prefix "table"
```

This command uses the *Prefix* parameter to get storage tables whose name starts with table.

## PARAMETERS

### -Context
Specifies the storage context.
To create it, you can use the New-AzureStorageContext cmdlet.

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

### -Name
Specifies the table name.
If the table name is empty, the cmdlet lists all the tables.
Otherwise, it lists all tables that match the specified name or the regular name pattern.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: N,Table

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies a prefix used in the name of the table or tables you want to get.
You can use this to find all tables that start with the same string, such as table.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageTable](36ff9a70-74d8-4b37-9962-c01b531c9a01)

[Remove-AzureStorageTable](f287198d-609e-4ac1-9221-9ce5453a732e)

