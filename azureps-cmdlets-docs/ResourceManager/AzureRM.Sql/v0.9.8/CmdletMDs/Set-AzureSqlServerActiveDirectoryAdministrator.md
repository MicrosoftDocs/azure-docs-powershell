---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Get-AzureSqlServerActiveDirectoryAdministrator.md
schema: 2.0.0
---

# Set-AzureSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Provisions an Azure AD administrator for SQL Server.

## SYNTAX

```
Set-AzureSqlServerActiveDirectoryAdministrator [-DisplayName] <String> [[-ObjectId] <Guid>]
 [-ServerName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlServerActiveDirectoryAdministrator** cmdlet provisions an Azure Active Directory (Azure AD) administrator for Azure SQL Server in the current subscription.

Only one administrator can be provisioned at a time.

The following members of Azure AD can be provisioned as an administrator for SQL Server: 

- Native members of Azure AD 
- Federated members of Azure AD 
- Imported members from other Azure AD who are native or federated members 
- Azure AD groups created as security groups

Microsoft accounts, such as those in the Outllook.com, Hotmail.com, or Live.com domains, are not supported as administrators.
Other guest accounts, such as those in the Gmail.com or Yahoo.com domains, are not supported as administrators.

We recommend that you provision a dedicated Azure AD group as an administrator.

## EXAMPLES

### Example 1: Provision an administrator group for a server
```
PS C:\>Set-AzureSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server06" -DisplayName "DBAs" 
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server06   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command provisions an Azure AD administrator group DBAs for the server named Server06 that is associated with resource group ResourceGroup01.

### Example 2: Provision an administrator group for a server
```
PS C:\>Set-AzureSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server06" -DisplayName "David Chew"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server06   David Chew  11E95548-B179-4FE1-9AF4-ACA49D13ABB9
```

This command provisions an Azure AD user David Chew as an administrator for the server named Server06.

### Example 3: Provision an administrator group by specifying its ID
```
PS C:\>Set-AzureSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server06" -DisplayName "DBAs" -ObjectId "40b79501-b343-44ed-9ce7-da4c8cc7353b"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server06   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command provisions an Azure AD administrator group DBAs for the server named Server06.
This command specifies an ID for the *ObjectId* parameter.
If the display name of the object is not unique, the command still works.

## PARAMETERS

### -DisplayName
Specifies the display name of the Azure AD administrator that this cmdlet provisions for SQL Server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Specifies the unique ID of the Azure AD administrator that this cmdlet provisions for SQL Server.
If the display name is not unique, you must specify a value for this parameter.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the SQL Server for which this cmdlet provisions an administrator.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the SQL Server for which this cmdlet provisions an administrator.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### InputType
System.String

## OUTPUTS

### OutputType
Microsoft.Azure.Commands.Sql.ServerActiveDirectoryAdministrator.Model.AzureSqlServerActiveDirectoryAdministratorModel

## NOTES

## RELATED LINKS

[Get-AzureSqlServerActiveDirectoryAdministrator](.\Get-AzureSqlServerActiveDirectoryAdministrator.md)

[Remove-AzureSqlServerActiveDirectoryAdministrator](.\Remove-AzureSqlServerActiveDirectoryAdministrator.md)

