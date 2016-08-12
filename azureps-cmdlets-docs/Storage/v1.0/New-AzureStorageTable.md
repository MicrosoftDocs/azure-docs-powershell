---
external help file: RMAzure_Storage.xml
online version: 5e8a9e67-ad04-4430-b057-a63cfb99585e
schema: 2.0.0
---

# New-AzureStorageTable
## SYNOPSIS
Creates a storage table.

## SYNTAX

```
New-AzureStorageTable [-Name] <String> [-Context <AzureStorageContext>]
```

## DESCRIPTION
The **New-AzureStorageTable** cmdlet creates a storage table associated with the storage account in azure_2.

## EXAMPLES

### Example 1: Create an azure storage table
```
PS C:\>New-AzureStorageTable -Name "tableabc"
```

This command creates a storage table with a name of tableabc.

### Example 2: Create multiple azure storage tables
```
PS C:\>"table1 table2 table3".split() | New-AzureStorageTable
```

This command creates multiple tables.
It uses the **Split** method of the .NET **String** class and then passes the names on the pipeline.

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
Specifies a name for the new table.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Table

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

[Get-AzureStorageTable](5e8a9e67-ad04-4430-b057-a63cfb99585e)

[Remove-AzureStorageTable](f287198d-609e-4ac1-9221-9ce5453a732e)

