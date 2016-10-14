---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Remove-AzureSqlDatabase

## SYNOPSIS
Deletes an Azure SQL Database.

## SYNTAX

### ByObjectWithConnectionContext
```
Remove-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-Database] <Database> [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNameWithConnectionContext
```
Remove-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-DatabaseName] <String> [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNameWithServerName
```
Remove-AzureSqlDatabase [-ServerName] <String> [-DatabaseName] <String> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectWithServerName
```
Remove-AzureSqlDatabase [-ServerName] <String> [-Database] <Database> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureSqlDatabase** cmdlet deletes an Azure SQL Database by server connection context or server name.
You can create an Azure SQL Database server connection context using the New-AzureSqlDatabaseServerContext cmdlet, and then use it with this cmdlet.

When you delete a database by specifying an Azure SQL Database server name, the **Remove-AzureSqlDatabase** cmdlet uses the name and the current Azure subscription information to perform the operation.

## EXAMPLES

### Example 1: Remove a database
```
PS C:\>Remove-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
```

This command removes the database named Database01 from the Azure SQL Database server connection context $Context.

### Example 2: Remove a database by using a server name
```
PS C:\>Remove-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
```

This command removes the database named Database01 from the Azure SQL Database server namedlpqd0zbr8y.

### Example 3: Remove a database by using the pipeline
```
PS C:\>$Database01 | Remove-AzureSqlDatabase -ConnectionContext $Context
PS C:\> $Database01 | Remove-AzureSqlDatabase -ServerName "lpqd0zbr8y"
```

This example demonstrates the alternative method of passing the database object through the pipeline.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server from which this cmdlet removes a database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByObjectWithConnectionContext, ByNameWithConnectionContext
Aliases: Context

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Database
Specifies an object that represents the database that this cmdlet removes.

```yaml
Type: Database
Parameter Sets: ByObjectWithConnectionContext, ByObjectWithServerName
Aliases: InputObject

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Allows the action to complete without prompting the user for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database that this cmdlet removes.

```yaml
Type: String
Parameter Sets: ByNameWithConnectionContext, ByNameWithServerName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server on which this cmdlet deletes the database.

```yaml
Type: String
Parameter Sets: ByNameWithServerName, ByObjectWithServerName
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
Type: AzureSMProfile
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

## NOTES
* Because of the severity of the operation, by default, this cmdlet prompts you for confirmation. To skip confirmation, specify the *Force* parameter.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Delete Database](https://msdn.microsoft.com/en-us/library/azure/dn505705.aspx)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](.\Get-AzureSqlDatabase.md)

[New-AzureSqlDatabase](.\New-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](.\New-AzureSqlDatabaseServerContext.md)

[Set-AzureSqlDatabase](.\Set-AzureSqlDatabase.md)

