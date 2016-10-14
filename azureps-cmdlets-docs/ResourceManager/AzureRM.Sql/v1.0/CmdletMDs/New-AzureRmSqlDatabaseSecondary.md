---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 999c2f73-f7f3-438f-ba9d-8f6451ebbc31
schema: 2.0.0
---

# New-AzureRmSqlDatabaseSecondary

## SYNOPSIS
Creates a secondary database for an existing database and starts data replication.

## SYNTAX

```
New-AzureRmSqlDatabaseSecondary [-DatabaseName] <String> [-SecondaryServiceObjectiveName <String>]
 [-SecondaryElasticPoolName <String>]
 [-Tags <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 -PartnerResourceGroupName <String> -PartnerServerName <String> [-AllowConnections <AllowConnections>]
 [-ServerName] <String> [-ResourceGroupName] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRMSqlDatabaseSecondary** cmdlet replaces the Start-AzureSqlDatabaseCopy cmdlet when used for setting up geo-replication for a database.
It returns the geo-replication link object from the primary to the secondary database.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DatabaseName
Specifies the name of the database to act as primary.

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

### -SecondaryServiceObjectiveName
Specifies the name of the service objective to assign to the secondary database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryElasticPoolName
Specifies the name of the elastic pool in which to put the secondary database.

```yaml
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
Specifies the tags to associate with the nextref_database replication link.

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

### -PartnerResourceGroupName
Specifies the name of the azure_2 Resource Group to which this cmdlet assigns the secondary database.

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

### -PartnerServerName
Specifies the name of the azure_2 SQL database server to act as secondary.

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

### -AllowConnections
Specifies the read intent of the secondary ssSDS.
psdx_paramvalues

- No
- All

```yaml
Type: AllowConnections
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the ssNoVersion of the primary  nextref_database.

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
Specifies the name of the azure_2 Resource Group to which this cmdlet assigns the primary database.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
You can pipe instances of the **Database** object for the primary database to this cmdlet.

## OUTPUTS

###  
This cmdlet returns **ReplicationLink** objects.

## NOTES

## RELATED LINKS

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

[Remove-AzureRmSqlDatabaseSecondary](.\Remove-AzureRmSqlDatabaseSecondary.md)

[Set-AzureRmSqlDatabaseSecondary](.\Set-AzureRmSqlDatabaseSecondary.md)

