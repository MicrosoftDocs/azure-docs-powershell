---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlDatabase

## SYNOPSIS
Sets properties for an Azure SQL database, or moves an existing database into an elastic pool.

## SYNTAX

```
Set-AzureSqlDatabase [-DatabaseName] <String> [-MaxSizeBytes <Int64>] [-Edition <DatabaseEdition>]
 [-RequestedServiceObjectiveName <String>] [-ElasticPoolName <String>]
 [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>] [-ServerName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlDatabase cmdlet sets properties for an Azure SQL database.
You can specify the ElasticPoolName parameter to move a database into an elastic pool.
If database is already in an elastic pool, you can specify the RequestedServiceObjectiveName parameter to assign a performance level.

## EXAMPLES

### Example 1: Update a database to a Standard S2 database
```
PS C:\>Set-AzureSqlDatabase -ResourceGroupName "ResourceGroup11" -DatabaseName "Database04" -ServerName "Server01" -Edition "Standard" -RequestedServiceObjectiveName "S2"
```

This command updates a database named Database04 to a Standard S2 database in a server named Server01.

### Example 2: Add a database to an elastic pool
```
PS C:\>Set-AzureSqlDatabase -ResourceGroupName "ResourceGroup11" -DatabaseName "Database05" -ServerName "Server01" -ElasticPoolName "ElasticPool01"
```

The following command adds a database named Database05 to the elastic pool named ElasticPool01 in the server named Server01.

## PARAMETERS

### -DatabaseName
Specifies the name of the database.

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

### -MaxSizeBytes
Specifies the new maximum size for the database in bytes.
You can specify either this parameter or MaxSizeGB.
See the MaxSizeGB parameter for acceptable values based on edition.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edition
Specifies the edition for the database.
Valid values are: 
- Default
- None
- Premium
- Basic
- Standard

```yaml
Type: DatabaseEdition
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestedServiceObjectiveName
The name of the service objective to assign to the Azure SQL Database.```yaml
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
The name of the Azure SQL elastic pool to put the database in.```yaml
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
The tags to associate with the Azure SQL Database.```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that contains the database.

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
Name of resource group of the Azure SQL Server that contains the Azure SQL Database.```yaml
Type: String
Parameter Sets: (All)
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

### System.String

## OUTPUTS

### System.Object

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabase]()

[New-AzureSqlDatabase]()

[Remove-AzureSqlDatabase]()

[Resume-AzureSqlDatabase]()

[Suspend-AzureSqlDatabase]()

[Azure SQL Database]()

