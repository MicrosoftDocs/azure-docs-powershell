---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlElasticPoolRecommendation

## SYNOPSIS
Gets elastic pool recommendations.

## SYNTAX

```
Get-AzureSqlElasticPoolRecommendation [-ServerName] <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlElasticPoolRecommendation cmdlet gets elastic pool recommendations for a server.
These recommendations include the following values: 

- DatabaseCollection.
Collection of database names that belong to the pool.
- DatabaseDtuMin.
Data Transmission Unit (DTU) guarantee for database in elastic pool. 
- DatabaseDtuMax.
DTU cap for database in elastic pool. 
- Dtu.
DTU guarantee for elastic pool. 
- StorageMb.
Storage in megabytes for elastic pool. 
- Edition.
Edition for elastic pool.
Valid values are: Basic, Standard, and Premium. 
- IncludeAllDatabases.
Whether to include all databases in the server in the elastic pool. 
- Name.
Name of the elastic pool.

## EXAMPLES

### Example 1: Get recommendations for a server
```
PS C:\>Get-AzureSqlElasticPoolRecommendation -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

This command gets the elastic pool recommendations for the server named Server01.

## PARAMETERS

### -ServerName
Specifies the name of the server for which this cmdlet gets recommendations.

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
Specifies name of the resource group that contains the server.

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

## OUTPUTS

## NOTES

## RELATED LINKS

