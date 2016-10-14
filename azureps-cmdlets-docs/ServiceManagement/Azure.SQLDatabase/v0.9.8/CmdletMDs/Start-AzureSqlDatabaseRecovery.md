---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: .\Start-AzureSqlDatabaseRestore.md
schema: 2.0.0
---

# Start-AzureSqlDatabaseRecovery

## SYNOPSIS
Initiates a restore request for a database.

## SYNTAX

### BySourceDatabaseName
```
Start-AzureSqlDatabaseRecovery -SourceServerName <String> -SourceDatabaseName <String>
 [-TargetServerName <String>] [-TargetDatabaseName <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### BySourceDatabaseObject
```
Start-AzureSqlDatabaseRecovery -SourceDatabase <RecoverableDatabase> [-TargetServerName <String>]
 [-TargetDatabaseName <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSqlDatabaseRecovery** cmdlet initiates a restore request for a live or dropped database.
This cmdlet supports basic recovery that uses the last known available backup for the database.
The recovery operation creates a new database.
If you recover a live database on the same server, you must specify a different name for the new database.

To do a point in time restore for a database, use the **Start-AzureSqlDatabaseRestore** cmdlet instead.

## EXAMPLES

### Example 1: Recover a database specified as an object
```
PS C:\>$Database = Get-AzureSqlRecoverableDatabase -ServerName "Server01" -DatabaseName "Database17" 
PS C:\> $Operation = Start-AzureSqlDatabaseRecovery -SourceDatabase $Database -TargetDatabaseName "DatabaseRestored"
```

The first command gets a database object by using the **Get-AzureSqlRecoverableDatabase** cmdlet.
The command stores that object in the $Database variable.

The second command recovers the database stored in $Database.

### Example 2: Recover a database specified by name
```
PS C:\>$Operation = Start-AzureSqlDatabaseRecovery -SourceServerName "Server01" -SourceDatabaseName "Database17" -TargetDatabaseName "DatabaseRestored"
```

This command recovers a database using the database name.

## PARAMETERS

### -SourceServerName
Specifies the name of the server on which the source database is live and running, or on which the source database ran before it was deleted.

```yaml
Type: String
Parameter Sets: BySourceDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDatabaseName
Specifies the name of the database that this cmdlet recovers.

```yaml
Type: String
Parameter Sets: BySourceDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetServerName
The name of the server you want to restore the database to. This can be the same server as the source database or a different server name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseName
Specifies the name of the recovered database.
If the source database is still live, in order to recover it to the same server, you must specify a name that differs from the source database name.

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

### -SourceDatabase
Specifies the database object that represents the database that this cmdlet recovers.

```yaml
Type: RecoverableDatabase
Parameter Sets: BySourceDatabaseObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.WindowsAzure.Management.Sql.Models.RecoverableDatabase

## OUTPUTS

### Microsoft.WindowsAzure.Management.Sql.Models.RecoverDatabaseOperation

## NOTES
* You must use certificate based authentication to run this cmdlet. Run the following commands on the computer where run this cmdlet: 

PS C:\\\> $subId = \<Subscription ID\>
PS C:\\\> $thumbprint = \<Certificate Thumbprint\>
PS C:\\\> $myCert = Get-Item Cert:\CurrentUser\My\$thumbprint
PS C:\\\> Set-AzureSubscription -SubscriptionName "mySubscription" -SubscriptionId $subId -Certificate $myCert
PS C:\\\> Select-AzureSubscription -SubscriptionName "mySubscription"

## RELATED LINKS

[Start-AzureSqlDatabaseRestore](.\Start-AzureSqlDatabaseRestore.md)

[Get-AzureSqlRecoverableDatabase](.\Get-AzureSqlRecoverableDatabase.md)

