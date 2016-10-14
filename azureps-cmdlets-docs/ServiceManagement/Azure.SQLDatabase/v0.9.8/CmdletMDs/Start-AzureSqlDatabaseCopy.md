---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: http://msdn.microsoft.com/library/dn546726.aspx
schema: 2.0.0
---

# Start-AzureSqlDatabaseCopy

## SYNOPSIS
Starts a copy operation of an Azure SQL Database.

## SYNTAX

### ByInputObject
```
Start-AzureSqlDatabaseCopy [-ServerName] <String> [-Database] <Database> [-PartnerServer <String>]
 -PartnerDatabase <String> [-Force] [-Profile <AzureProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObjectContinuous
```
Start-AzureSqlDatabaseCopy [-ServerName] <String> [-Database] <Database> -PartnerServer <String>
 [-PartnerDatabase <String>] [-ContinuousCopy] [-OfflineSecondary] [-Force] [-Profile <AzureProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByDatabaseNameContinuous
```
Start-AzureSqlDatabaseCopy [-ServerName] <String> [-DatabaseName] <String> -PartnerServer <String>
 [-PartnerDatabase <String>] [-ContinuousCopy] [-OfflineSecondary] [-Force] [-Profile <AzureProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByDatabaseName
```
Start-AzureSqlDatabaseCopy [-ServerName] <String> [-DatabaseName] <String> [-PartnerServer <String>]
 -PartnerDatabase <String> [-Force] [-Profile <AzureProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSqlDatabaseCopy** cmdlet starts a one-time copy operation or a continuous copy operation of a specific Azure SQL Database.
This cmdlet is not transactional.

The original database is the source database.
The copy is the secondary or target database.
For a continuous copy, the source and target databases cannot reside on the same server, and the servers that host the source and target databases must be part of the same subscription.

If you do not specify the *ContinuousCopy* parameter, this cmdlet creates a one-time copy of the source database.
When the response is received, the operation can still be in progress.
You can monitor the operation by using the Get-AzureSqlDatabaseCopy or Get-AzureSqlDatabaseOperation cmdlet.

If you specify *ContinuousCopy*, this cmdlet creates a continuous copy of the source database.
When the response is received, the operation will be in progress.
You can monitor the operation by using **Get-AzureSqlDatabaseCopy** or **Get-AzureSqlDatabaseOperation**.

You can create a continuous copy as an online or offline database.
The online continuous copy is used to configure Active Geo-Replication for Azure SQL Database.
The offline continuous copy is used to configure Standard Geo-Replication for Azure SQL Database.

## EXAMPLES

### Example 1: Schedule a continuous database copy
```
PS C:\>Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf65" -ContinuousCopy
```

This command schedules a continuous copy of the database named Orders on the server named lpqd0zbr8y.
The command create a target database on the server named bk0b8kf658.

### Example 2: Create a one-time copy on the same server
```
PS C:\>Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerDatabase "OrdersCopy"
```

This command creates a one-time copy of the database named Orders on the server named lpqd0zbr8y.
The command creates a copy named OrdersCopy on the same server.

### Example 3: Schedule a continuous offline database copy
```
PS C:\>Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf65" -ContinuousCopy -OfflineSecondary
```

This command schedules a continuous copy of the database named Orders on the server named lpqd0zbr8y.
This command creates an offline target database on the server named bk0b8kf658.

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

### -Database
Specifies an object that represents the source Azure SQL Database.
This parameter accepts pipeline input.

```yaml
Type: Database
Parameter Sets: ByInputObject, ByInputObjectContinuous
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PartnerServer
Specifies the name of the server that hosts the target database.
This server must be in the same Azure subscription as the source database server.

```yaml
Type: String
Parameter Sets: ByInputObject, ByDatabaseName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerDatabase
Specifies name of the target database.
If you specify the *ContinuousCopy* parameter, the value for *PartnerDatabase* must match the name of the source database.
If you do not specify *ContinuousCopy*, you must specify a name for the target database, which can be different from the source database name.

```yaml
Type: String
Parameter Sets: ByInputObject, ByDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
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

### -ContinuousCopy
Specifies that the database copy is a continuous copy.
The source and target databases in a continuous copy relationship must reside on different servers in the same subscription.
If you do not specify this parameter, this cmdlet creates a one-time copy.
For a one-time copy, the source and secondary databases can be on any server in the same subscription.

```yaml
Type: SwitchParameter
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OfflineSecondary
Indicates that this cmdlet creates an offline continuous copy.
If you specify both *OfflineSecondary* and *ContinuousCopy*, this cmdlet creates an offline continuous copy.
This is used to configure Standard Geo-Replication for Azure SQL Database.

If you do not specify *OfflineSecondary* and specify *ContinuousCopy*, this cmdlet creates an online continuous copy.
This is used to configure Active Geo-Replication for Azure SQL Database.

If you specify *OfflineSecondary* but not *ContinuousCopy*, the command fails.

```yaml
Type: SwitchParameter
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the source database.

```yaml
Type: String
Parameter Sets: ByDatabaseNameContinuous, ByDatabaseName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

## NOTES
* Authentication: This cmdlet requires certificate-based authentication. For an example of how to use certificate-based authentication to set the current subscription, see New-AzureSqlDatabaseServerContext cmdlet.
* Monitoring: To check for the status of one or more continuous copy relationships that are active on the server, use the **Get-AzureSqlDatabaseCopy** cmdlet. To verify the status of the operations at both the source and target of the continuous copy relationship, use the **Get-AzureSqlDatabaseOperation** cmdlet.

## RELATED LINKS

[Azure SQL Database Cmdlets](http://msdn.microsoft.com/library/dn546726.aspx)

[Get-AzureSqlDatabaseCopy](.\Get-AzureSqlDatabaseCopy.md)

[Stop-AzureSqlDatabaseCopy](.\Stop-AzureSqlDatabaseCopy.md)

