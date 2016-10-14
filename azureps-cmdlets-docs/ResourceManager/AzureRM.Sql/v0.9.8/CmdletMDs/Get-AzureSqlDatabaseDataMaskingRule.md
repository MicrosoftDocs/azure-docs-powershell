---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlDatabaseDataMaskingRule

## SYNOPSIS
Gets the data masking rules from an Azure SQL database.

## SYNTAX

```
Get-AzureSqlDatabaseDataMaskingRule [-RuleId <String>] [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlDatabaseDataMaskingRule cmdlet gets either a specific data masking rule, or all of the data masking rules of an Azure SQL database.
To use the cmdlet, use the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database, and the RuleId parameter to specify which rule this cmdlet returns.
If you do not provide RuleId, then all the data masking rules of that Azure SQL database are returned.

## EXAMPLES

### Example 1: Get all data masking rules from a database
```
PS C:\>Get-AzureSqlDatabaseDataMaskingRule -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database06"
```

This command gets all data masking rules from Database06 in resource group ResourceGroup11 contained in server Server01.

## PARAMETERS

### -RuleId
Specifies the ID of the requested rule.
If you do not specify this parameter, this cmdlet gets all the information about all the data masking rules in the specified SQL database.

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

### -ServerName
Specifies the name of the server.

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

### -ResourceGroupName
Specifies the name of the resource group containing the database.

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

### None

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Security.Model.DatabaseDataMaskingRuleModel

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabaseDataMaskingPolicy]()

[New-AzureSqlDatabaseDataMaskingRule]()

[Remove-AzureSqlDatabaseDataMaskingRule]()

[Set-AzureSqlDatabaseDataMaskingPolicy]()

[Set-AzureSqlDatabaseDataMaskingRule]()

[Azure SQL Database]()

