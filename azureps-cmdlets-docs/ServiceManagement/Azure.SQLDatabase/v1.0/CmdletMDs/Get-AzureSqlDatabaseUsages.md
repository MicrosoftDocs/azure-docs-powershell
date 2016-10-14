---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: http://msdn.microsoft.com/library/ee336279.aspx
schema: 2.0.0
---

# Get-AzureSqlDatabaseUsages

## SYNOPSIS
Gets the size and size limit of a SQL Database.

## SYNTAX

```
Get-AzureSqlDatabaseUsages [-ServerName] <String> -DatabaseName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseUsages** cmdlet gets the current size and size limit of an azure_2 SQL Database.

## EXAMPLES

### Example 1: Get usage information for a SQL Database
```
PS C:\>Get-AzureSqlDatabaseUsages -ServerName "Server01" -DatabaseName "Database01"
```

This command gets the size and size limit information for the SQL Database named Database01 on Server01.

## PARAMETERS

### -DatabaseName
Specifies the name of the azure_2 SQL Database.

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

### -Profile
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that hosts the azure_2 SQL Database.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

