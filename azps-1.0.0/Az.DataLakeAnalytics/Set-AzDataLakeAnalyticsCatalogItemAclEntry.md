---
external help file: Microsoft.Azure.Commands.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
online version:
schema: 2.0.0
---

# Set-AzDataLakeAnalyticsCatalogItemAclEntry

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### SetCatalogAclEntryForUser (Default)
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-User] -ObjectId <Guid>
 -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetCatalogItemAclEntryForUser
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-User] -ObjectId <Guid> -ItemType <String>
 -Path <CatalogPathInstance> -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetCatalogAclEntryForGroup
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-Group] -ObjectId <Guid>
 -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetCatalogItemAclEntryForGroup
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-Group] -ObjectId <Guid> -ItemType <String>
 -Path <CatalogPathInstance> -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetCatalogAclEntryForOther
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-Other] -Permissions <PermissionType>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetCatalogItemAclEntryForOther
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-Other] -ItemType <String>
 -Path <CatalogPathInstance> -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetCatalogAclEntryForUserOwner
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-UserOwner] -Permissions <PermissionType>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetCatalogItemAclEntryForUserOwner
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-UserOwner] -ItemType <String>
 -Path <CatalogPathInstance> -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetCatalogAclEntryForGroupOwner
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-GroupOwner] -Permissions <PermissionType>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetCatalogItemAclEntryForGroupOwner
```
Set-AzDataLakeAnalyticsCatalogItemAclEntry [-Account] <String> [-GroupOwner] -ItemType <String>
 -Path <CatalogPathInstance> -Permissions <PermissionType> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Account
Specifies the Data Lake Analytics account name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Set ACL entry of catalog for group.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetCatalogAclEntryForGroup, SetCatalogItemAclEntryForGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupOwner
Set ACL entry of catalog for group owner.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetCatalogAclEntryForGroupOwner, SetCatalogItemAclEntryForGroupOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ItemType
The type of the catalog item(s).

```yaml
Type: System.String
Parameter Sets: SetCatalogItemAclEntryForUser, SetCatalogItemAclEntryForGroup, SetCatalogItemAclEntryForOther, SetCatalogItemAclEntryForUserOwner, SetCatalogItemAclEntryForGroupOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
The identity of the user to set.

```yaml
Type: System.Guid
Parameter Sets: SetCatalogAclEntryForUser, SetCatalogItemAclEntryForUser, SetCatalogAclEntryForGroup, SetCatalogItemAclEntryForGroup
Aliases: Id, UserId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Other
Set ACL entry of catalog for other.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetCatalogAclEntryForOther, SetCatalogItemAclEntryForOther
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
The catalog item path to search within, in the format:'DatabaseName.\<optionalSecondPart\>.\<optionalThirdPart\>.\<optionalFourthPart\>'.

```yaml
Type: Microsoft.Azure.Commands.DataLakeAnalytics.Models.CatalogPathInstance
Parameter Sets: SetCatalogItemAclEntryForUser, SetCatalogItemAclEntryForGroup, SetCatalogItemAclEntryForOther, SetCatalogItemAclEntryForUserOwner, SetCatalogItemAclEntryForGroupOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permissions
The permissions to set for the ACE.
Possible values include: 'None', 'Read', 'ReadWrite'.

```yaml
Type: Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+PermissionType
Parameter Sets: (All)
Aliases:
Accepted values: None, Read, ReadWrite

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -User
Set ACL entry of catalog for user.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetCatalogAclEntryForUser, SetCatalogItemAclEntryForUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserOwner
Set ACL entry of catalog for user owner.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetCatalogAclEntryForUserOwner, SetCatalogItemAclEntryForUserOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Guid

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.CatalogPathInstance

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+PermissionType

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.PSDataLakeAnalyticsAcl

## NOTES

## RELATED LINKS
