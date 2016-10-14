---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Get-AzureSqlDatabaseIndexRecommendations.md
schema: 2.0.0
---

# Stop-AzureSqlDatabaseExecuteIndexRecommendation

## SYNOPSIS
Stops the workflow that runs a recommended index operation.

## SYNTAX

```
Stop-AzureSqlDatabaseExecuteIndexRecommendation -ServerName <String> -DatabaseName <String>
 -IndexRecommendationName <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureSqlDatabaseExecuteIndexRecommendation** cmdlet stops the workflow that runs a recommended index operation.

## EXAMPLES

### Example 1: Stop running an index recommendation
```
PS C:\>Stop-AzureSqlDatabaseExecuteIndexRecommendation -ResourceGroup "ResourceGroup01" -ServerName "Server11" -DatabaseName " Database06" -IndexRecommendationName "INDEX_NAME"
```

This command stops running the index recommendation.

## PARAMETERS

### -DatabaseName
Specifies the name of the database for which this cmdlet stops the workflow.

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

### -IndexRecommendationName
Specifies the name of the index recommendation that this cmdlet stops.

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
This cmdlet stops a workflow on a database that this server hosts.

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
Specifies the server that hosts the database for which this cmdlet stops a workflow.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSqlDatabaseIndexRecommendations](.\Get-AzureSqlDatabaseIndexRecommendations.md)

[Start-AzureSqlDatabaseExecuteIndexRecommendation](.\Start-AzureSqlDatabaseExecuteIndexRecommendation.md)

