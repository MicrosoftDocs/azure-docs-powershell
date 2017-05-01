---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: AFF400A9-F0E4-4EA1-A224-A380C323AA70
online version: 
schema: 2.0.0
---

# Get-AzureRmDataLakeStoreItemAcl

## SYNOPSIS
Gets the ACL of a file or folder in Data Lake Store.

## SYNTAX

```
Get-AzureRmDataLakeStoreItemAcl -Account <String> [-Path] <DataLakeStorePathInstance> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmDataLakeStoreItemAcl** cmdlet gets the access control list (ACL) of a filer or folder in Data Lake Store.

## EXAMPLES

### Example 1: Get the ACL for a folder
```
PS C:\>Get-AzureRmDataLakeStoreItemAcl -AccountName "ContosoADL" -Path /
```

This command gets the ACL for the root directory of the specified Data Lake Store account.

## PARAMETERS

### -Path
Specifies the Data Lake Store path of the file or folder, starting with the root directory (/).

```yaml
Type: DataLakeStorePathInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Account
Specifies the name of the Data Lake Store account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureRmDataLakeStoreItemAcl](./Set-AzureRmDataLakeStoreItemAcl.md)


