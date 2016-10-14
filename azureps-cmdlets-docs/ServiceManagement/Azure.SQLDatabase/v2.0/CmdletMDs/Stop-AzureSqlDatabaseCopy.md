---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Stop-AzureSqlDatabaseCopy

## SYNOPSIS
Terminates a continuous copy relationship.

## SYNTAX

### ByInputObject
```
Stop-AzureSqlDatabaseCopy [-ServerName] <String> [-DatabaseCopy] <DatabaseCopy> [-ForcedTermination] [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDatabase
```
Stop-AzureSqlDatabaseCopy [-ServerName] <String> [-Database] <Database> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-ForcedTermination] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByDatabaseName
```
Stop-AzureSqlDatabaseCopy [-ServerName] <String> [-DatabaseName] <String> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-ForcedTermination] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureSqlDatabaseCopy** cmdlet terminates a continuous copy relationship.
This cmdlet stops the data movement between the source database and secondary or target database, and then changes the state of the secondary database to be a stand-alone online database.

There are two ways to end a continuous copy relationship, termination or planned termination and forced termination with possible data loss.
On the server that hosts the source database, you can run this cmdlet in termination or forced termination mode.
On the server that hosts the secondary database, you must use forced termination mode.

A planned termination waits until all committed transactions on the source database, at the time that you run the cmdlet, have been replicated to the secondary database.
Forced termination does not wait for replication of any outstanding committed transactions, and can cause possible data loss in the secondary database.

While replication status is PENDING, only forced termination can successfully end a continuous copy relationship.
If the replication status is PENDING, termination that is not forced is not supported.

## EXAMPLES

### Example 1: Terminate a continuous copy relationship
```
PS C:\>Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf658"
```

This command terminates the continuous copy relationship of database named Orders on the server named lpqd0zbr8y.
The server named bk0b8kf658 hosts the secondary database.

### Example 2: Forcibly terminate a continuous copy relationship
```
PS C:\>$DatabaseCopy = Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders"
PS C:\> $DatabaseCopy | Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -ForcedTermination
```

The first command gets the database copy relationship for the database named Orders on the server named lpqd0zbr8y.

The second command forcibly terminates a continuous copy relationship from the server that hosts the secondary database.

## PARAMETERS

### -ServerName
Specifies the name of the server on which the source database resides.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DatabaseCopy
Specifies an object that represents a database.
This cmdlet terminates the continuous copy relationship of the database that this parameter specifies.
This parameter accepts pipeline input.

```yaml
Type: DatabaseCopy
Parameter Sets: ByInputObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ForcedTermination
Indicates that this cmdlet causes forced termination of the continuous copy relationship.
Forced termination may cause with data loss.
To run this cmdlet on a server that hosts the target database, you must specify this parameter.
To run this cmdlet on a server that hosts the source database, if the secondary database is unavailable, you must specify this parameter.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -Database
Specifies an object that represents the source Azure SQL Database.
This cmdlet terminates the continuous copy relationship of the database that this parameter specifies.

```yaml
Type: Database
Parameter Sets: ByDatabase
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PartnerServer
Specifies the name of the server that hosts the target database.

```yaml
Type: String
Parameter Sets: ByDatabase, ByDatabaseName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerDatabase
Specifies name of the secondary database.
If you specify a name, it must match the name of the source database.

```yaml
Type: String
Parameter Sets: ByDatabase, ByDatabaseName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of a database.
This cmdlet terminates the continuous copy relationship of the database that this parameter specifies.

```yaml
Type: String
Parameter Sets: ByDatabaseName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### None

## NOTES
* Authentication: This cmdlet requires certificate-based authentication. For an example of how to use certificate-based authentication to set the current subscription, see the New-AzureSqlDatabaseServerContext cmdlet.
* Restrictions: On the server that hosts the secondary database, only forced termination is supported.
* Impact of termination on the former secondary database: After termination, the secondary database becomes an independent database. If seeding already completed on the secondary database, after termination this database is open for full access. If the source database is a read-write database, the former secondary database becomes a read-write database, too.

  If seeding is currently in progress, seeding is aborted, and the former secondary database never becomes visible on the server that hosts the secondary database.

* You can set the source database to read-only mode. This guarantees that source and secondary databases are synchronized after termination, and makes sure that no transactions are committed during termination. Once the termination finishes, set the source back to read-write mode. Optionally, you can also set the former secondary database to read-write mode.
* Monitoring: To verify the status of the operations at both the source and target of the continuous copy relationship, use the Get-AzureSqlDatabaseOperation cmdlet.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Stop Database Copy](https://msdn.microsoft.com/en-us/library/dn509573.aspx)

[Azure SQL Database Cmdlets](.\Azure.SQLDatabase.md)

[Get-AzureSqlDatabaseCopy](.\Get-AzureSqlDatabaseCopy.md)

[Start-AzureSqlDatabaseCopy](.\Start-AzureSqlDatabaseCopy.md)

