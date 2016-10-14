---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlElasticPool

## SYNOPSIS
Modifies properties for an elastic database pool in Azure SQL Database.

## SYNTAX

```
Set-AzureSqlElasticPool [-ElasticPoolName] <String> [-Edition <DatabaseEdition>] [-Dtu <Int32>]
 [-StorageMB <Int64>] [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>]
 [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>] [-ServerName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlElasticPool cmdlet modifies properties for an elastic database pool in Azure SQL Database.
This cmdlet can modify the minimum Database Throughput Units (DTUs) per database, and the maximum DTUs per database, the number of DTUs for the pool, and the storage limit for the pool.

## EXAMPLES

### Example 1: Modify properties for an elastic pool
```
PS C:\>Set-AzureSqlDatabaseElasticPool -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -ElasticPoolName "ElasticPool27" -Dtu 1000 -DatabaseDtuMax 100 -DatabaseDtuMin 20
```

This command modifies properties for an elastic pool named ElasticPool27.
The command sets the number of DTUs for the elastic pool to be 1000 and sets the minimum and maximum DTUs.

## PARAMETERS

### -ElasticPoolName
Specifies the name of the elastic pool that this cmdlet modifies.

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

### -Edition
Specifies the edition of Azure SQL Database for the elastic pool.
You cannot change the edition.

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

### -Dtu
Specifies the total number of shared DTUs for the elastic pool.
The default values for different editions are as follows: 

- Basic.
100 DTUs 
- Standard.
100 DTUs
- Premium.
125 DTUs

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageMB
Specifies the storage limit, in megabytes, for the elastic pool.
For more information, see the New-AzureSqlElasticPool cmdlet.

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

### -DatabaseDtuMin
Specifies the minimum number of DTUs that the elastic pool guarantees to all the databases in the pool.
The default value is zero (0).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseDtuMax
Specifies the maximum number of DTUs that any single database in the pool can consume.
The default values for different editions are as follows: 

- Basic.
5 DTUs 
- Standard.
100 DTUs
- Premium.
125 DTUs

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
Specifies a dictionary of tags that this cmdlet associates with the elastic pool.

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

### -ServerName
Specifies the name of the server that contains the elastic pool that this cmdlet updates.

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
Specifies the name of the resource group that contains the elastic pool that this cmdlet modifies.

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

[Azure SQL Database]()

[Get-AzureSqlElasticPool]()

[Get-AzureSqlElasticPoolActivity]()

[Get-AzureSqlElasticPoolDatabase]()

[New-AzureSqlElasticPool]()

