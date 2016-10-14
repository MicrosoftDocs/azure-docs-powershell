---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Use-AzureSqlServerAuditingPolicy

## SYNOPSIS
Specifies that a database uses the auditing policy of its hosting server.

## SYNTAX

```
Use-AzureSqlServerAuditingPolicy [-PassThru] [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Use-AzureSqlServerAuditingPolicy cmdlet specifies that a database uses the auditing policy of its host server.
Specify the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database.
If no auditing policy is defined for the database server, this cmdlet fails.

## EXAMPLES

### Example 1: Define for a database to use the auditing policy of its server
```
PS C:\>Use-AzureSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01"
```

This command specifies that the database named Database01 on Server02 uses the auditing policy of its server.

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
Specifies the name of the server that hosts the database to use the auditing policy.

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
Specifies the name of the database to use the auditing policy.

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
Specifies the name of the resource group that contains the database to use the auditing policy.

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

[Get-AzureSqlDatabaseAuditingPolicy]()

[Get-AzureSqlServerAuditingPolicy]()

[Set-AzureSqlDatabaseAuditingPolicy]()

[Set-AzureSqlServerAuditingPolicy]()

