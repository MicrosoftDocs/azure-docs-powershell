---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmDataLakeStoreItemExpiry

## SYNOPSIS
Sets or removes the expire time for a file in an Azure Data Lake Store account.

## SYNTAX

```
Set-AzureRmDataLakeStoreItemExpiry [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [[-Expiration] <DateTimeOffset>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Set-AzureRmDataLakeStoreItemExpiry cmdlet sets or removes the expire time for a file in an Azure Data Lake Store account.

## EXAMPLES

### --------------------------  Example 1: Set the expiration time for a file  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Set-AzureRmDataLakeStoreItemExpiry -AccountName "ContosoADL" -Path /myfile.txt -Expiration [DateTimeOffset]::Now.AddHours(2)
```

Sets expiration on the file myfile.txt in account ContosoADL to be two hours from now.
This will cause the file to expire (be marked for delete) in two hours.

### --------------------------  Example 2: Remove the expiration on a file  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Set-AzureRmDataLakeStoreItemExpiry -AccountName "ContosoADL" -Path /myfile.txt
```

Removes any expiration that was previously set on file 'myfile.txt' in account 'ContosoADL'.
This means the file will not automatically expire (be marked for delete) and will need to be manually deleted or set to expire again.

## PARAMETERS

### -Account
Specifies the Data Lake Store account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Expiration
The absolute expiration time for the specified file.
If no value or set to MaxValue, the file will never expire.

```yaml
Type: DateTimeOffset
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the Data Lake Store path of the file item for which to set or remove expiry.

```yaml
Type: DataLakeStorePathInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreItem

## NOTES
Alias: Set-AdlStoreItemExpiry

## RELATED LINKS

[Get-AzureRmDataLakeStoreItem]()

