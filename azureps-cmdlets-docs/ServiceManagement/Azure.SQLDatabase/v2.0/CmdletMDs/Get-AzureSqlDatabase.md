---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Get-AzureSqlDatabase

## SYNOPSIS
Retrieves one or more databases.

## SYNTAX

### ByConnectionContext (Default)
```
Get-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-Database <Database>]
 [-DatabaseName <String>] [-RestorableDropped] [-RestorableDroppedDatabase <RestorableDroppedDatabase>]
 [-DatabaseDeletionDate <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabase [-ServerName] <String> [-Database <Database>] [-DatabaseName <String>]
 [-RestorableDropped] [-RestorableDroppedDatabase <RestorableDroppedDatabase>]
 [-DatabaseDeletionDate <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabase** cmdlet retrieves one or more instances of an Azure SQL Database from an Azure SQL Database server.
You can specify the server with an Azure SQL Database server connection context that you create using the **New-AzureSqlDatabaseServerContext** cmdlet.
Or, if you specify the Azure SQL Database server name, the cmdlet uses the current Azure subscription information to authenticate the request to access the server.

If you do not specify a database, the **Get-AzureSqlDatabase** cmdlet returns all databases from the specified server.

Retrieving restorable dropped databases:

Retrieve restorable dropped databases by using the *RestorableDropped* parameter.
To return all restorable dropped databases use the *RestorableDropped* parameter without *DatabaseName* and *DatabaseDeletionDate*.
To return a specific restorable dropped database use the *RestorableDropped* parameter with the *DatabaseName* and *DatabaseDeletionDate* parameters.
When retrieving a specific restorable dropped database by using the *DatabaseName* parameter you must also include the *DatabaseDeletionDate* parameter and the specified *DatabaseDeletionDate* value must include milliseconds to match the desired database.

The **Get-AzureSqlDatabase** cmdlet returns either all restorable dropped databases on a server, or one specific database that matches both *DatabaseName* and *DatabaseDeletionDate*.
To return restorable dropped databases that satisfy different criteria, such as all restorable dropped databases of a specific name, you must return all restorable dropped databases, and then filter the results on the client.

## EXAMPLES

### Example 1: Retrieve all databases on a server
```
PS C:\>Get-AzureSqlDatabase -ServerName "lpqd0zbr8y"
```

This command retrieves all databases on the server named lpqd0zbr8y.

### Example 2: Retrieve all restorable dropped databases on a server
```
PS C:\>Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped
```

This command retrieves all restorable dropped databases on the server named lpqd0zbr8y.

### Example 3: Retrieve a database from a server specified by a connection context
```
PS C:\>$Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
```

This command retrieves database named Database01 from the server specified by the connection context $Context.

### Example 4: Store a database object in a variable
```
PS C:\>$Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
```

This command retrieves database named Database01 from the server named lpqd0zbr8y.
The command stores the database object in the $Database01 variable.

### Example 5: Retrieve a restorable dropped database
```
PS C:\>$DroppedDB = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01" -DatabaseDeletionDate "2012-11-09T22:59:43.000Z" -RestorableDropped
```

This command retrieves the restorable dropped database named Database01 that was deleted on 11/9/2012 from the server named lpqd0zbr8y.
This command stores the results in the $DroppedDB variable.

### Example 6: Retrieve all restorable dropped databases on a server and filter the results
```
PS C:\>Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped | Where-Object {$_.Name -eq "ContactDB"}
```

This command retrieves all restorable dropped databases on the server named lpqd0zbr8y, and then filters the results to only the databases named ContactDB.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server from which to retrieve a database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Database
Specifies an object that represents the database that this cmdlet retrieves.

```yaml
Type: Database
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database that this cmdlet retrieves.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorableDropped
Indicates that this cmdlet returns *RestorableDroppedDatabase* objects instead of *Database* objects.
You can use the *DatabaseDeletionDate* parameter to select a specific restorable dropped database.

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

### -RestorableDroppedDatabase
Specifies an object that represents the restorable dropped database that this cmdlet retrieves.

```yaml
Type: RestorableDroppedDatabase
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseDeletionDate
Specifies the date and time of a deletion.
If you specify the *RestorableDropped* parameter, specify this parameter to retrieve a restorable dropped database based on the deletion date and time.

The *DatabaseDeletionDate* parameter must include milliseconds to match the time of the desired database.
Specifying a value without milliseconds results in the database not being found.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that contains the database that this cmdlet retrieves.
The cmdlet uses the current Azure subscription to access the server.

```yaml
Type: String
Parameter Sets: ByServerName
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase

## OUTPUTS

### IEnumerable<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database>
This cmdlet returns a *Database* object if you do not specify the *RestorableDropped* parameter.

### IEnumerable<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase>
This cmdlet returns a *RestorableDroppedDatabase* object if you specify the *RestorableDropped* parameter.

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabase](.\New-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](.\New-AzureSqlDatabaseServerContext.md)

[Remove-AzureSqlDatabase](.\Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](.\Set-AzureSqlDatabase.md)

