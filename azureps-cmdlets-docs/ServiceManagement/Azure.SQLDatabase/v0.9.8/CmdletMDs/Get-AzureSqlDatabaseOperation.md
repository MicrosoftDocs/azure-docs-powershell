---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: http://msdn.microsoft.com/library/ee336279.aspx
schema: 2.0.0
---

# Get-AzureSqlDatabaseOperation

## SYNOPSIS
Gets the status of database operations on an Azure server.

## SYNTAX

### ByConnectionContext (Default)
```
Get-AzureSqlDatabaseOperation [-ConnectionContext] <IServerDataServiceContext> [-Database <Database>]
 [-DatabaseName <String>] [-OperationGuid <Guid>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabaseOperation [-ServerName] <String> [-Database <Database>] [-DatabaseName <String>]
 [-OperationGuid <Guid>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseOperation** cmdlet gets the status of database operations on the specified Azure server.
If you specify only the *ServerName* or *ConnectionContext* parameter, the cmdlet gets all the database operations for the server.
If you also specify a database by using the *Database* or *DatabaseName* parameter, this cmdlet gets all the operations for the specified database.
If you specify an operation GUID, and *ServerName* or *ConnectionContext*, the cmdlet gets a single database operation.

## EXAMPLES

### Example 1: Get the status of all database operations for a database
```
PS C:\>$Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context -DatabaseName "Database17"
```

This command gets the status of all database operations on the database named Database17 on the server that the connection context $Context specifies.

### Example 2: Get the status of all database operations for a server
```
PS C:\>$Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context
```

This command gets the status of all database operations on the server that the connection context $Context specifies.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server.

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
Specifies an object that represents an Azure SQL Database.
If you specify this parameter, you must specify the *ServerName* parameter or *ConnectionContext* parameter.

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
Specifies the name of a database.
If you specify this parameter, you must specify the *ServerName* parameter or the *ConnectionContext* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationGuid
Specifies the operation ID that represents a specific database operation for which this cmdlet gets status.
You can obtain operation IDs by requesting all the database operations for a Azure SQL Database or server.
If you specify this parameter, you must specify the *ServerName* parameter or the *ConnectionContext* parameter.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of a server.

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
In-memory profile.```yaml
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

### System.Guid

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database.DatabaseOperationResponseList[]
This cmdlet returns an array of **DatabaseOperationResponseList** objects if you get multiple operations.

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database.DatabaseOperationResponse

## NOTES

## RELATED LINKS

[Azure SQL Database](http://msdn.microsoft.com/library/ee336279.aspx)

[Get-AzureSqlDatabase](.\Get-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](.\New-AzureSqlDatabaseServerContext.md)

