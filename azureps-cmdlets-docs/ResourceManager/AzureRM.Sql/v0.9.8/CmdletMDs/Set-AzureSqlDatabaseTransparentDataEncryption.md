---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlDatabaseTransparentDataEncryption

## SYNOPSIS
Modifies TPE for an Azure SQL database.

## SYNTAX

```
Set-AzureSqlDatabaseTransparentDataEncryption [-State] <TransparentDataEncryptionStateType>
 [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlDatabaseTransparentDataEncryption cmdlet modifies the Transparent Data Encryption (TDE) property of an Azure SQL database.
For more information, see Transparent Data Encryption with Azure SQL Database (https://msdn.microsoft.com/library/dn948096) in the Microsoft Developer Network Library.

## EXAMPLES

### Example 1: Enable TPE for a database
```
PS C:\>Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "Server12" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "Database01" -State "Enabled"
```

This command enables TPE for the database named Database01 on the server named Server12.

## PARAMETERS

### -State
Specifies the value of the TDE property.
Valid values are: 

- Enabled 
- Disabled

```yaml
Type: TransparentDataEncryptionStateType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that hosts the database that this cmdlet modifies.

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
Specifies the name of the database that this cmdlet modifies.

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
Specifies the name of the resource group that contains the database that this cmdlet modifies.

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

[Get-AzureSqlDatabaseTransparentDataEncryption]()

[Get-AzureSqlDatabaseTransparentDataEncryptionActivity]()

