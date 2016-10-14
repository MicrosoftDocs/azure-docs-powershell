---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Get-AzureSqlDatabaseCopy

## SYNOPSIS
Checks the status of copy relationships.

## SYNTAX

### ByServerNameOnly (Default)
```
Get-AzureSqlDatabaseCopy [-ServerName] <String> [[-DatabaseName] <String>] [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByInputObject
```
Get-AzureSqlDatabaseCopy [-ServerName] <String> [-DatabaseCopy] <DatabaseCopy> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByDatabase
```
Get-AzureSqlDatabaseCopy [-ServerName] <String> [-Database] <Database> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseCopy** cmdlet checks the status of one or more active copy relationships.
Run this cmdlet after you run the Start-AzureSqlDatabaseCopy or Stop-AzureSqlDatabaseCopy cmdlet.
You can check a specific copy relationship, all copy relationships, or a filtered list of copy relationships, such as all copies on a specific target server.
You can run this cmdlet on the server that hosts the source or target database.

This cmdlet is synchronous.
The cmdlet blocks the Azure PowerShell console until it returns a status object.

The *PartnerServer* and *PartnerDatabase* parameters are optional.
If you do not specify either parameter, this cmdlet returns a table of results.
To see the status for only a particular database, specify both parameters.

## EXAMPLES

### Example 1: Get the copy status of a database
```
PS C:\>Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf658"
```

This command gets the status of the database named Orders on the server named lpqd0zbr8y.
The *PartnerServer* parameter restricts this command to the bk0b8kf658 server.

### Example 2: Get the status of all copies on a serverGet the status of all copies on a server
```
PS C:\>Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y"
```

This command gets the status of all active copies on the server named lpqd0zbr8y.

## PARAMETERS

### -ServerName
Specifies the name of the server on which the database copy resides.

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

### -DatabaseName
Specifies the name of the source database.
This cmdlet gets that copy status of the database that this parameter specifies.

```yaml
Type: String
Parameter Sets: ByServerNameOnly
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerServer
Specifies the name of the server that hosts the target database.
If this server is not found in the sys.dm_database_copies dynamic management view, this cmdlet returns an empty status object.

```yaml
Type: String
Parameter Sets: ByServerNameOnly, ByDatabase
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerDatabase
Specifies name of the secondary database.
If this database is not found in the sys.dm_database_copies dynamic management view, this cmdlet returns an empty status object.

```yaml
Type: String
Parameter Sets: ByServerNameOnly, ByDatabase
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseCopy
Specifies an object that represents a database.
This cmdlet gets the copy status of the database that this parameter specifies.
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

### -Database
Specifies an object that represents the source Azure SQL Database.
This cmdlet gets the copy status of the database that this parameter specifies.

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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

## NOTES
* Authentication: This cmdlet requires certificate-based authentication. For an example of how to use certificate-based authentication to set the current subscription, see the New-AzureSqlDatabaseServerContext cmdlet.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Azure SQL Database Cmdlets](.\Azure.SQLDatabase.md)

[Start-AzureSqlDatabaseCopy](.\Start-AzureSqlDatabaseCopy.md)

[Stop-AzureSqlDatabaseCopy](.\Stop-AzureSqlDatabaseCopy.md)

