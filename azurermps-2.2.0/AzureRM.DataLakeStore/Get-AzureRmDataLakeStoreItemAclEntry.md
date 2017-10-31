---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmDataLakeStoreItemAclEntry

## SYNOPSIS
Gets the access control list (ACL) of a file or folder in Data Lake Store.

## SYNTAX

```
Get-AzureRmDataLakeStoreItemAclEntry [-Account] <String> [-Path] <DataLakeStorePathInstance>
```

## DESCRIPTION
The Get-AzureRmDataLakeStoreItemAcl cmdlet gets the access control list (ACL) of a filer or folder in Data Lake Store.

## EXAMPLES

### --------------------------  Example 1: Get the ACL for a folder  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmDataLakeStoreItemAclEntry -AccountName "ContosoADL" -Path /
```

This command gets the ACL for the root directory of the specified Data Lake Store account.

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

### -Path
Specifies the Data Lake Store path of the file or folder, starting with the root directory (/).

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

## INPUTS

## OUTPUTS

### System.Collections.Generic.IEnumerable`1[[Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreItemAce, Microsoft.Azure.Commands.DataLakeStore, Version=2.0.1.0, Culture=neutral, PublicKeyToken=null]]

## NOTES

## RELATED LINKS

