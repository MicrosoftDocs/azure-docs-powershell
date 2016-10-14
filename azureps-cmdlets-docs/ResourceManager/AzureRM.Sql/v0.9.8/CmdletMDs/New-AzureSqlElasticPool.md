---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureSqlElasticPool

## SYNOPSIS
Creates an elastic database pool in Azure SQL Database.

## SYNTAX

```
New-AzureSqlElasticPool -ElasticPoolName <String> [-Edition <DatabaseEdition>] [-Dtu <Int32>]
 [-StorageMB <Int64>] [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>]
 [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>] [-ServerName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureSqlElasticPool cmdlet creates an elastic database pool in Azure SQL Database.

## EXAMPLES

### Example 1: Create an elastic pool
```
PS C:\>New-AzureSqlElasticPool -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -ElasticPoolName "ElasticPool27" -Edition "Standard" -Dtu 400 -DatabaseDtuMin 10 -DatabaseDtuMax 100
```

This command creates an elastic pool in the Standard service tier named ElasticPool27.
The server named Server01 hosts the elastic pool in an Azure resource group named ResourceGroup11.
The command specifies DTU property values for the pool and the databases in the pool.

## PARAMETERS

### -ElasticPoolName
Specifies the name of the elastic pool that this cmdlet creates.

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

### -Edition
Specifies the edition of Azure SQL Database for the elastic pool.
Valid values are: 

- Premium 
- Basic 
- Standard

For the current preview, the edition must be Standard.

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
You cannot specify a value for this parameter for the Premium edition.

If you do not specify this parameter, this cmdlet calculates a value based on the value of the Dtu parameter.
We recommend that you do not specify the StorageMB parameter.

If you specify StorageMB, but do not specify Dtu, the cmdlet calculates a value for Dtu.
If you specify values for both, the values must be consistent.
For more information about the relationship between storage and DTUs, see eDTU and storage limits for elastic pools and elastic databases.

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
Specifies the maximum number of Database Throughput Units (DTUs) that any single database in the pool can consume.
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
Specifies the name of the server in which this cmdlet creates the elastic pool.

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
Specifies the name of the resource group that contains the elastic pool that this cmdlet creates.

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

[Remove-AzureSqlElasticPool]()

[Set-AzureSqlElasticPool]()

