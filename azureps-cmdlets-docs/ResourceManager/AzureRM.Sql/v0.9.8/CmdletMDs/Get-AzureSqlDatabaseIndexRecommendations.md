---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Start-AzureSqlDatabaseExecuteIndexRecommendation.md
schema: 2.0.0
---

# Get-AzureSqlDatabaseIndexRecommendations

## SYNOPSIS
Gets the recommended index operations for a server or database.

## SYNTAX

```
Get-AzureSqlDatabaseIndexRecommendations -ServerName <String> [-DatabaseName <String>] [-TableName <String>]
 [-IndexRecommendationName <String>] [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseIndexRecommendations** cmdlet gets the recommended index operations for a server or database in Azure SQL Database.

## EXAMPLES

### Example 1: Get index recommendations for all databases on server
```
PS C:\>Get-AzureSqlDatabaseIndexRecommendations -ResourceGroupName "ResourceGroup01" -ServerName "Server06"
```

This command returns index recommendations for all databases on server.

### Example 2: Get index recommendations for a specific database
```
PS C:\>Get-AzureSqlDatabaseIndexRecommendations -ResourceGroupName "ResourceGroup01" -ServerName "Server06" -DatabaseName "Database01"
```

This command returns index recommendations for specific database.

### Example 3: Get a single index recommendation by name
```
PS C:\>Get-AzureSqlDatabaseIndexRecommendations -ResourceGroupName "ResourceGroup01" -ServerName "Server06" -DtabaseName "Database01" -IndexRecommendationName "INDEX_NAME"
```

This command returns single index recommendation by name.

## PARAMETERS

### -DatabaseName
Specifies the name of the database for which this cmdlet gets the index recommendations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IndexRecommendationName
Specifies the name of the index recommendation that this cmdlet gets.

```yaml
Type: String
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
Specifies the name of the resource group that contains the server.
This cmdlet gets index recommendations for a database that this server hosts.

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
Specifies the server that hosts the database for which this cmdlet gets index recommendations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TableName
Specifies the name of an Azure SQL Table.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Start-AzureSqlDatabaseExecuteIndexRecommendation](.\Start-AzureSqlDatabaseExecuteIndexRecommendation.md)

[Stop-AzureSqlDatabaseExecuteIndexRecommendation](.\Stop-AzureSqlDatabaseExecuteIndexRecommendation.md)

