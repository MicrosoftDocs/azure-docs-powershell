---
external help file: RMAzure_Storage.xml
online version: 5e8a9e67-ad04-4430-b057-a63cfb99585e
schema: 2.0.0
---

# Remove-AzureStorageTable
## SYNOPSIS
Removes a storage table.

## SYNTAX

```
Remove-AzureStorageTable [-Name] <String> [-Context <AzureStorageContext>] [-Force] [-PassThru] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageTable** cmdlet removes one or more storage tables from a storage account in azure_2.

## EXAMPLES

### Example 1: Remove a table
```
PS C:\>Remove-AzureStorageTable -Name "TableABC"
```

This command removes a table.

### Example 2: Remove several tables
```
PS C:\>Get-AzureStorageTable table* | Remove-AzureStorageTable
```

This example uses a wildcard character with the *Name* parameter to get all tables that match the pattern table and then passes the result on the pipeline to remove the tables.

## PARAMETERS

### -Context
Specifies the azure_2 storage context.
You can create it by using the New-AzureStorageContext cmdlet.

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

### -Name
Specifies the name of the table to remove.

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

[Get-AzureStorageTable](5e8a9e67-ad04-4430-b057-a63cfb99585e)

