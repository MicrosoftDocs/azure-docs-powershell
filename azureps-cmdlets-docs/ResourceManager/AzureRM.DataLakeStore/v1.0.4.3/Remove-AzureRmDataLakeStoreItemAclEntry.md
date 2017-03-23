---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmDataLakeStoreItemAclEntry

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Remove ACL Entries using ACL object (Default)
```
Remove-AzureRmDataLakeStoreItemAclEntry [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-Acl] <DataLakeStoreItemAcl> [-Force] [<CommonParameters>]
```

### Remove specific ACE
```
Remove-AzureRmDataLakeStoreItemAclEntry [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-AceType] <AceType> [[-Id] <Guid>] [-Default] [-Force] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Account
The DataLakeStore account to execute the filesystem operation in

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

### -AceType
Indicates the type of ACE to remove (user, group, mask, other)

```yaml
Type: AceType
Parameter Sets: Remove specific ACE
Aliases: 
Accepted values: User, Group, Mask, Other

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Acl
The ACL spec containing the entries to remove.
These entries MUST exist in the ACL spec for the file already.
This can be a modified ACL from Get-AzureDataLakeStoreItemAcl or it can be the string  representation of an ACL as defined in the apache webhdfs specification.
Note that this is only supported for named ACEs.This cmdlet is not to be used for setting the owner or owning group.

```yaml
Type: DataLakeStoreItemAcl
Parameter Sets: Remove ACL Entries using ACL object
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default
Indicates that the ACL entry is a default ACE to be removed.

```yaml
Type: SwitchParameter
Parameter Sets: Remove specific ACE
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that the ACL entries should be removed on the file with the specified ACL without prompting.

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

### -Id
The identity of the user or group to remove.
Optional.
If none is passed this will attempt to remove an unamed ACE, which is necessary for both mask and other ACEs

```yaml
Type: Guid
Parameter Sets: Remove specific ACE
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
The path in the specified Data Lake account that should have ACL entries removed.
Can be a file or folder In the format '/folder/file.txt', where the first '/' after the DNS indicates the root of the file system.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance
Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreItemAcl
Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreEnums+AceType
System.Guid
System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

