---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureSqlDatabaseAuditing

## SYNOPSIS
Removes auditing of an Azure SQL database.

## SYNTAX

```
Remove-AzureSqlDatabaseAuditing [-PassThru] [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureSqlDatabaseAuditing cmdlet removes the auditing of an Azure SQL database.
To use this cmdlet, use the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database.
After you run this cmdlet, auditing of the database is not performed.
If the command succeeds and you have used the PassThru parameter, the cmdlet returns an object describing the current auditing policy, as well as the database identifiers.
Database identifiers include, but are not limited to, the ResourceGroupName, ServerName and DatabaseName.

## EXAMPLES

### Example 1: Remove the auditing of an Azure SQL database
```
PS C:\>Remove-AzureSqlDatabaseAuditing -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01"
```

This command removes the auditing of database named Database01.
That database is located on Server02 in the resource group named ResourceGroup11.

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server containing the database.

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

### Microsoft.Azure.Commands.Sql.Security.Model.DatabaseAuditingPolicyModel

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabaseAuditingPolicy]()

[Set-AzureSqlDatabaseAuditingPolicy]()

[Azure SQL Database]()

