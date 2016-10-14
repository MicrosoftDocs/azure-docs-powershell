---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Remove-AzureRmSqlServerActiveDirectoryAdministrator.md
schema: 2.0.0
---

# Get-AzureRmSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Gets information about an azure_2 AD administrator for SQL Server.

## SYNTAX

```
Get-AzureRmSqlServerActiveDirectoryAdministrator [-ServerName] <String> [-ResourceGroupName] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSqlServerActiveDirectoryAdministrator** cmdlet gets information about an azure_2 Active Directory (azure_2 AD) administrator for an azure_2ssNoVersion in the current subscription.

## EXAMPLES

### Example 1: Gets information about an administrator for a server
```
PS C:\>Get-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command gets information about an azure_2 AD administrator for a server named Server01 that is associated with a resource group named ResourceGroup01.

## PARAMETERS

### -ServerName
Specifies the name of the ssNoVersion for which this cmdlet gets information.

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
Specifies the name of the resource group to which the ssNoVersion is assigned.

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

[Remove-AzureRmSqlServerActiveDirectoryAdministrator](.\Remove-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Set-AzureRmSqlServerActiveDirectoryAdministrator](.\Set-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

