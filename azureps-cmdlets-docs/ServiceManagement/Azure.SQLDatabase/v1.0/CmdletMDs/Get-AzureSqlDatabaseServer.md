---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Get-AzureSqlDatabaseServer

## SYNOPSIS
Gets information about ssSDS servers.

## SYNTAX

```
Get-AzureSqlDatabaseServer [[-ServerName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseServer** cmdlet gets information about the instances of ssSDS Server in the current subscription.
If you specify a server by name, this cmdlet returns an object that contains information about that server.
Otherwise, the cmdlet returns information about all the servers.

## EXAMPLES

### Example 1: Get information about all servers
```
PS C:\>Get-AzureSqlDatabaseServer
```

This command returns information about all instances of ssSDS Server in the current subscription.

### Example 2: Get information about a specific server
```
PS C:\>Get-AzureSqlDatabaseServer -ServerName "lpqd0zbr8y"
```

This command returns information about the server named lpqd0zbr8y.

## PARAMETERS

### -ServerName
Specifies the name of the server that this cmdlet removes.
Specify the server name, not the fully qualified DNS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## OUTPUTS

### IEnumerable<Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext>

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[List Servers](https://msdn.microsoft.com/en-us/library/azure/dn505702.aspx)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabaseServer](.\New-AzureSqlDatabaseServer.md)

[Remove-AzureSqlDatabaseServer](.\Remove-AzureSqlDatabaseServer.md)

[Set-AzureSqlDatabaseServer](.\Set-AzureSqlDatabaseServer.md)

