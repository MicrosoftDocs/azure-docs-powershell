---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementUser

## SYNOPSIS
Gets one or more users.

## SYNTAX

### Get all users (Default)
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [<CommonParameters>]
```

### Get user by ID
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [-UserId <String>] [<CommonParameters>]
```

### Find users
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [-FirstName <String>] [-LastName <String>]
 [-State <PsApiManagementUserState>] [-Email <String>] [-GroupId <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementUser** cmdlet gets a specific user, or all users, if no user is specified.

## EXAMPLES

### Example 1: Get all users
```
PS C:\> Get-AzureRmApiManagementUser -Context $apimContext
```

This command gets all users.

### Example 2: Get a specific user by ID
```
PS C:\> Get-AzureRmApiManagementUser -Context $apimContext -UserId "0123456789"
```

This command gets the user identified by the ID "0123456789".

### Example 3: Get users by last name
```
PS C:\> Get-AzureRmApiManagementUser -Context $apimContext -LastName "Fuller"
```

This command gets all users that have the last name "Fuller".

### Example 4: Get a specific user by email address
```
PS C:\> Get-AzureRmApiManagementUser -Context $apimContext -Email "user@contoso.com"
```

This command gets the user that has the email address "user@contoso.com".

### Example 5: Get all users within a group
```
PS C:\> Get-AzureRmApiManagementUser -Context $apimContext -GroupId "0001"
```

This command gets all users within the group identified by the ID "0001".

## PARAMETERS

### -Context
Specifies an **PsApiManagementContext** object that contains details about the context of the Azure API Management service.

```yaml
Type: PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Email
Specifies the email address of the user to get.

```yaml
Type: String
Parameter Sets: Find users
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FirstName
Specifies the first name of the users to get.
If this parameter is included, the cmdlet gets all users that have the specified first name.

```yaml
Type: String
Parameter Sets: Find users
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupId
Specifies the ID of a group.
If this parameter is included, the cmdlet gets all users within the group.

```yaml
Type: String
Parameter Sets: Find users
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LastName
Specifies the last name of the users to get.
If this parameter is included, the cmdlet gets all users that have the specified last name.

```yaml
Type: String
Parameter Sets: Find users
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the users.
If this parameter is included, the cmdlet gets all users in the specified state.

```yaml
Type: PsApiManagementUserState
Parameter Sets: Find users
Aliases:
Accepted values: Active, Blocked

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserId
Specifies the ID of the user to get.

```yaml
Type: String
Parameter Sets: Get user by ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

## OUTPUTS

### System.Collections.Generic.IList

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementUser](./New-AzureRmApiManagementUser.md)

[Remove-AzureRmApiManagementUser](./Remove-AzureRmApiManagementUser.md)

[Set-AzureRmApiManagementUser](./Set-AzureRmApiManagementUser.md)
