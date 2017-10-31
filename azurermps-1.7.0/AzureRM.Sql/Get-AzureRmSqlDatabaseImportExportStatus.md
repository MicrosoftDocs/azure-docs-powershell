---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
ms.assetid: 3D74E98C-15CB-4720-BD58-1227B501DD1C
online version: 
schema: 2.0.0
---

# Get-AzureRmSqlDatabaseImportExportStatus

## SYNOPSIS
Gets the details of an import or export of an Azure SQL Database.

## SYNTAX

```
Get-AzureRmSqlDatabaseImportExportStatus [-OperationStatusLink] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSqlDatabaseImportExportStatus** cmdlet gets details of a bacpac file import from a storage account to an Azure SQL Database or an export of an Azure SQL Database as a bacpac file to a storage account.

This cmdlet is also supported by the SQL Server Stretch Database service on Azure.

## EXAMPLES

### Example 1: Get the import and export status of a SQL database
```
PS C:\>Get-AzureRmSqlDatabaseImportExportStatus -OperationStatusLink "https://management.contoso.com/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resource01/providers/Microsoft.Sql/servers/server01/databases/database01/importExportOperationResults/00000000-000-0000-0000-000000000000?api-version=2014-04-01"
OperationStatusLink :
ErrorMessage        :
LastModifiedTime    : 4/15/2016 10:16:14 PM
QueuedTime          : 4/15/2016 10:16:13 PM
StatusMessage       : Running, Progress = 5.00 %
Status              : InProgress
```

This command gets the status of an import or export request for a database at the specified URL.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
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
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationStatusLink
Specifies the status link that is returned from the [New-AzureRmSqlDatabaseExport](./New-AzureRmSqlDatabaseExport.md) or [New-AzureRmSqlDatabaseImport](./New-AzureRmSqlDatabaseImport.md) cmdlets.

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
* Keywords: azure, azurerm, arm, resource, management, manager, sql, database, mssql

## RELATED LINKS

[New-AzureRmSqlDatabaseExport](./New-AzureRmSqlDatabaseExport.md)

[New-AzureRmSqlDatabaseImport](./New-AzureRmSqlDatabaseImport.md)
