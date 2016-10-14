---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Get-AzureRmSqlServerActiveDirectoryAdministrator.md
schema: 2.0.0
---

# Set-AzureRmSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Provisions an azure_2 AD administrator for SQL Server.

## SYNTAX

```
Set-AzureRmSqlServerActiveDirectoryAdministrator [-DisplayName] <String> [[-ObjectId] <Guid>]
 [-ServerName] <String> [-ResourceGroupName] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmSqlServerActiveDirectoryAdministrator** cmdlet provisions an azure_2 Active Directory (azure_2 AD) administrator for azure_2ssNoVersion in the current subscription.

You can provision only one administrator at a time.

The following members of azure_2 AD can be provisioned as a SQL Server administrator:

- Native members of azure_2 AD 
- Federated members of azure_2 AD 
- Imported members from other azure_2 ADs who are native or federated members 
- azure_2 AD groups created as security groups

Microsoft accounts, such as those in the Outlook.com, Hotmail.com, or Live.com domains, are not supported as administrators.
Other guest accounts, such as those in the Gmail.com or Yahoo.com domains, are not supported as administrators.

We recommend that you provision a dedicated azure_2 AD group as an administrator.

## EXAMPLES

### Example 1: Provision an administrator group for a server
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "DBAs" 
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command provisions an azure_2 AD administrator group named DBAs for the server named Server01.
This server is associated with resource group ResourceGroup01.

### Example 2: Provision an administrator user for a server
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "David Chew"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
resourcegroup01   server01   David Chew  11E95548-B179-4FE1-9AF4-ACA49D13ABB9
```

This command provisions an azure_2 AD user as an administrator for the server named Server01.

### Example 3: Provision an administrator group by specifying its ID
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "DBAs" -ObjectId "40b79501-b343-44ed-9ce7-da4c8cc7353b"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command provisions an azure_2 AD administrator group named DBAs for the server named Server01.
The command specifies an ID for the *ObjectId* parameter.
This makes sure that that the command succeeds even if the display name of the group is not unique.

## PARAMETERS

### -DisplayName
Specifies the display name of the azure_2 AD administrator that this cmdlet provisions.

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
Specifies the unique ID of the azure_2 AD administrator that this cmdlet provisions.
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
Specifies the name of the ssNoVersion for which this cmdlet provisions an administrator.

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
Specifies the name of the resource group to which the server is assigned.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerActiveDirectoryAdministrator.Model.AzureSqlServerActiveDirectoryAdministratorModel

## NOTES

## RELATED LINKS

[Get-AzureRmSqlServerActiveDirectoryAdministrator](.\Get-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Remove-AzureRmSqlServerActiveDirectoryAdministrator](.\Remove-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

