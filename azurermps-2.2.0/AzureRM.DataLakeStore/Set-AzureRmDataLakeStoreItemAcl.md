---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: D7148E72-7504-48D7-9D6E-A96C955DA82A
online version:
schema: 2.0.0
---

# Set-AzureRmDataLakeStoreItemAcl

## SYNOPSIS
Modifies the ACL of a file or folder in Data Lake Store.

## SYNTAX

```
Set-AzureRmDataLakeStoreItemAcl -Account <String> [-Path] <DataLakeStorePathInstance>
 [-Acl] <DataLakeStoreItemAcl> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmDataLakeStoreItemAcl** cmdlet modifies the access control list (ACL) of a file or folder in Data Lake Store.

## EXAMPLES

### Example 1: Set the ACL for a file and a folder
```
PS C:\>$ACL = Get-AzureRmDataLakeStoreItemAcl -AccountName "ContosoADL" -Path /
PS C:\> Set-AzureRmDataLakeStoreItemAcl -AccountName "ContosoADL" -Path "/MyFiles/Test.txt" -Acl $ACL
```

The first command gets the ACL for the root directory of the ContosoADL account, and then stores it in the $ACL variable.

The second command sets the ACL for the file Test.txt to the one in $ACL.

## PARAMETERS

### -Acl
Specifies an ACL for a file or a folder.

```yaml
Type: DataLakeStoreItemAcl
Parameter Sets: (All)
Aliases:

Required: True
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

[Get-AzureRmDataLakeStoreItemAcl](./Get-AzureRmDataLakeStoreItemAcl.md)


