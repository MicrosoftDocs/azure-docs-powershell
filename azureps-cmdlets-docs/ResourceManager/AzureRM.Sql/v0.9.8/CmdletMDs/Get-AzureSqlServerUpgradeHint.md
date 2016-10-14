---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Get-AzureSqlDatabaseExpanded.md
schema: 2.0.0
---

# Get-AzureSqlServerUpgradeHint

## SYNOPSIS
Gets pricing tier hints for upgrading a SQL Database server.

## SYNTAX

```
Get-AzureSqlServerUpgradeHint [-ServerName] <String> [-ExcludeElasticPools <Boolean>]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlServerUpgradeHint** cmdlet gets pricing tier hints for upgrading an Azure SQL Database server.
Hints may contain the elastic database pool and stand-alone database hints.
Databases that are still in Web and Business pricing tiers get a hint to upgrade to the new Basic, Standard, or Premium pricing tiers, or to go into the elastic database pool.
This cmdlet returns hints for all databases that the specified server hosts.

## EXAMPLES

### Example 1: Get combined recommendations
```
PS C:\>Get-AzureSqlServerUpgradeHint -ResourceGroupName "ResourceGroup01" -ServerName "Server06"
ElasticPools Databases           
------------ ---------           
{}           {database01, database02}
```

This command gets combined recommendations for all the databases on server named Server06.

## PARAMETERS

### -ExcludeElasticPools
Indicates whether to exclude databases that are included in elastic database pool recommendations.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -ResourceGroupName
Specifies the name of the resource group that contains the server for which this cmdlet gets an upgrade hint.

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

### -ServerName
Specifies the name of the server for which this cmdlet gets an upgrade hint.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSqlDatabaseExpanded](.\Get-AzureSqlDatabaseExpanded.md)

[Get-AzureSqlElasticPoolRecommendation](.\Get-AzureSqlElasticPoolRecommendation.md)

