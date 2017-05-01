---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmDataLakeStoreItemAcl

## SYNOPSIS
Clears the access control list (ACL) of a file or folder in Data Lake Store.

## SYNTAX

```
Remove-AzureRmDataLakeStoreItemAcl -Account <String> [-Path] <DataLakeStorePathInstance> [-Default] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureRmDataLakeStoreItemAcl cmdlet clears the access control list (ACL) of a file or folder in Data Lake Store.

## EXAMPLES

### --------------------------  Example 1: Remove the ACL from a folder  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> Remove-AzureRmDataLakeStoreItemAcl -AccountName "ContosoADL" -Path /
```

This command removes the ACL for the root directory for the ContosoADL account.

## PARAMETERS

### -Default
Indicates that this operation removes the default ACL for a file or a folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the Data Lake Store path of the item, starting with the root directory (/).

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
Specifies the Data Lake Store account name.

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
Alias: Remove-AdlStoreAcl

## RELATED LINKS

[Get-AzureRmDataLakeStoreItemAcl]()

[Set-AzureRmDataLakeStoreItemAcl]()

