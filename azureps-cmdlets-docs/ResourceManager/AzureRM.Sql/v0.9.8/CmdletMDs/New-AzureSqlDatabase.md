---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureSqlDatabase

## SYNOPSIS
Creates an Azure SQL database or an elastic database.

## SYNTAX

```
New-AzureSqlDatabase -DatabaseName <String> [-CollationName <String>] [-CatalogCollation <String>]
 [-MaxSizeBytes <Int64>] [-Edition <DatabaseEdition>] [-RequestedServiceObjectiveName <String>]
 [-ElasticPoolName <String>] [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-ServerName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureSqlDatabase cmdlet creates a new Azure SQL database. 
You can also create an elastic database by setting the ElasticPoolName parameter to an existing elastic pool.

## EXAMPLES

### Example 1: Create an database in a specified server
```
PS C:\>New-AzureSqlDatabase -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

This command creates a database named Database01 in server Server01.

### Example 2: Create an elastic database in a specified server
```
PS C:\>New-AzureSqlDatabase -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01" -ElasticPoolName "ElasticPool22"
```

This command creates a database named Database01 in the elastic pool named ElasticPool22 in server Server02.

## PARAMETERS

### -DatabaseName
Specifies the name of the database.

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

### -CollationName
The name of the Azure SQL Database collation to use.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CatalogCollation
The name of the Azure SQL Database catalog collation to use.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSizeBytes
Specifies the maximum size of the database in bytes.

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
Specifies the edition to assign to the database.
Valid values are: 
- Default
- None
- Premium
- Basis
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
The name of the elastic pool to put the database in.```yaml
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
The tags to associate to the Azure SQL Database Server.```yaml
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
Specifies the name of the server to create the database.

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
Name of resource group that the Azure SQL Server is in.```yaml
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

[Remove-AzureSqlDatabase]()

[Resume-AzureSqlDatabase]()

[Set-AzureSqlDatabase]()

[Suspend-AzureSqlDatabase]()

[Azure SQL Database]()

[New-AzureSqlServer]()

[New-AzureSqlElasticPool]()

