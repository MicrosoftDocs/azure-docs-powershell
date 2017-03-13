---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
ms.assetid: 22ACB910-0C41-4649-8D22-537E38CB4570
online version: 
schema: 2.0.0
---

# New-AzureRmWebAppDatabaseBackupSetting

## SYNOPSIS
Creates an Azure Web App Backup setting.

## SYNTAX

```
New-AzureRmWebAppDatabaseBackupSetting [-Name] <String> [-DatabaseType] <String> [-ConnectionString] <String>
 [[-ConnectionStringName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmWebAppDatabaseBackupSetting** cmdlet creates an Azure Web App Backup setting.

## EXAMPLES

### Example 1: Create a database backup setting
```
PS C:\> New-AzureRmWebAppDatabaseBackupSetting -ResourceGroupName "Default-Web-WestUS" -Name "ContosoWebApp" -ConnectionString "MyConnectionString" -DatabaseType "SqlAzure"
```

This command creates a database backup setting (connection string) of type SqlAzure for the specified app ContosoWebApp that is within resource group Default-Web-WestUS.

## PARAMETERS

### -Name
Specifies the name of the Web App.

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

### -DatabaseType
Specifies the type of the database.
For instance, SqlAzure or MySql.

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

### -ConnectionString
Specifies the connection string.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
