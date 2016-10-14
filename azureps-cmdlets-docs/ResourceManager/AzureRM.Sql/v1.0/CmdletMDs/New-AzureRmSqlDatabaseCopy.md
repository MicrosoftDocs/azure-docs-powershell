---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\New-AzureRmSqlDatabaseSecondary.md
schema: 2.0.0
---

# New-AzureRmSqlDatabaseCopy

## SYNOPSIS
Creates a copy of a nextref_database that uses the snapshot at the current time.

## SYNTAX

```
New-AzureRmSqlDatabaseCopy [-DatabaseName] <String> [-ServiceObjectiveName <String>]
 [-ElasticPoolName <String>] [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-CopyResourceGroupName <String>] [-CopyServerName <String>] -CopyDatabaseName <String> [-ServerName] <String>
 [-ResourceGroupName] <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmSqlDatabaseCopy** cmdlet creates a copy of an ssSDS that uses the snapshot of the data at the current time.
Use this cmdlet instead of the Start-AzureSqlDatabaseCopy cmdlet to create a one-time database copy.
This cmdlet returns the **Database** object of the copy.

Note: Use the New-AzureRmSqlDatabaseSecondary cmdlet to configure geo-replication for a database.

This cmdlet is also supported by the SQL Server Stretch Database service on azure_2.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DatabaseName
Specifies the name of the nextref_database to copy.

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

### -ServiceObjectiveName
Specifies the name of the service objective to assign to the copy.

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

### -ElasticPoolName
Specifies the name of the elastic pool in which to assign the copy.

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

### -Tags
Specifies the tags to associate with the azure_2 SQL Database copy.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CopyResourceGroupName
Specifies the name of the azure_2 Resource Group in which to assign the copy.

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

### -CopyServerName
Specifies the name of the ssNoVersion which hosts the copy.

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

### -CopyDatabaseName
Specifies the name of the nextref_database copy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the  ssNoVersion that contains the database to copy.

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
Specifies the name of the  Resource Group to which this cmdlet assigns the copied database.

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

###  
You can pipe instances of the **Database** object for the source database to this cmdlet.

## OUTPUTS

###  
This cmdlet returns a **Database** object that represents the copied database.

## NOTES

## RELATED LINKS

[New-AzureRmSqlDatabaseSecondary](.\New-AzureRmSqlDatabaseSecondary.md)

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

