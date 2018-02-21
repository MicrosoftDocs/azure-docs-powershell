---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: E8F8059C-FFD7-4147-A4C2-A2780726CAEA
online version:
schema: 2.0.0
---

# Set-AzureRmDataLakeStoreItemAclEntry

## SYNOPSIS
Modifies an entry in the ACL of a file or folder in Data Lake Store.

## SYNTAX

### Set ACL Entries using ACL object
```
Set-AzureRmDataLakeStoreItemAclEntry -Account <String> [-Path] <DataLakeStorePathInstance>
 [-Acl] <DataLakeStoreItemAcl> [-Force] [<CommonParameters>]
```

### Set specific ACE
```
Set-AzureRmDataLakeStoreItemAclEntry -Account <String> [-Path] <DataLakeStorePathInstance> [-AceType] <AceType>
 [[-Id] <Guid>] [-Permissions] <Permission> [-Default] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmDataLakeStoreItemAclEntry** cmdlet modifies an entry (ACE) in the access control list (ACL) of a file or folder in Data Lake Store.

## EXAMPLES

### Example 1: Modify permissions for an ACE
```
PS C:\>Set-AzureRmDataLakeStoreItemAclEntry -AccountName "ContosoADL" -Path / -AceType User -Id (Get-AzureRmADUser -Mail "PattiFuller@contoso.com").ObjectId -Permissions All
```

This command modifies the ACE for Patti Fuller to have all permissions.

## PARAMETERS

### -AceType
Specifies the type of ACE to modify.
The acceptable values for this parameter are:

- User
- Group
- Mask
- Other

```yaml
Type: AceType
Parameter Sets: Set specific ACE
Aliases:
Accepted values: User, Group, Mask, Other

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Acl
Specifies the ACL object that contains the entries to modify.

```yaml
Type: DataLakeStoreItemAcl
Parameter Sets: Set ACL Entries using ACL object
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default
Indicates that this operation modifies the default ACE from the specified ACL.

```yaml
Type: SwitchParameter
Parameter Sets: Set specific ACE
Aliases:

Required: False
Position: 5
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
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Specifies the object ID of the AzureActive Directory user, group, or service principal for which to modify an ACE.

```yaml
Type: Guid
Parameter Sets: Set specific ACE
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the Data Lake Store path of the item for which to modify an ACE, starting with the root directory (/).

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

### -Permissions
Specifies the permissions for the ACE.
The acceptable values for this parameter are:

- None
- Execute
- Write
- WriteExecute
- Read
- ReadExecute
- ReadWrite
- All

```yaml
Type: Permission
Parameter Sets: Set specific ACE
Aliases:
Accepted values: None, Execute, Write, WriteExecute, Read, ReadExecute, ReadWrite, All

Required: True
Position: 5
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

[Remove-AzureRmDataLakeStoreItemAclEntry](./Remove-AzureRmDataLakeStoreItemAclEntry.md)


