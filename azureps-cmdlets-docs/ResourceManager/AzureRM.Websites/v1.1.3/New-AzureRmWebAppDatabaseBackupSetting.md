---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmWebAppDatabaseBackupSetting

## SYNOPSIS
Creates a new database backup setting for a web app.

## SYNTAX

```
New-AzureRmWebAppDatabaseBackupSetting [-Name] <String> [-DatabaseType] <String> [-ConnectionString] <String>
 [[-ConnectionStringName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmWebAppDatabaseBackupSetting** cmdlet creates a new database backup setting for a web app that was built using the Web Apps feature of the Azure App Service.

## EXAMPLES

### Example 1: Create a backup setting for the specified web app
```
PS C:\> New-AzureRmWebAppDatabaseBackupSetting -ResourceGroupName "Default-Web-WestUS" -Name "ContosoWebApp" -ConnectionString "MyConnectionString" -DatabaseType "SqlAzure"
```

This command creates a database backup setting (connection string) of type SqlAzure for the web app named "ContosoWebApp" that is in the "Default-Web-WestUS" resource group.

## PARAMETERS

### -ConnectionString
Specifies the connection string to the database that is being backed up.

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

### -ConnectionStringName
Specifies the name of the connection string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseType
Specifies the type of the database to be backed up. The valid values are: SqlAzure, MySql, LocalMySql, and PostgreSql.

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

### -Name
Specifies the name of the web app.

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

[Get-AzureRmWebAppBackup](./Get-AzureRmWebAppBackup.md)

[New-AzureRmWebAppBackup](./New-AzureRmWebAppBackup.md)
