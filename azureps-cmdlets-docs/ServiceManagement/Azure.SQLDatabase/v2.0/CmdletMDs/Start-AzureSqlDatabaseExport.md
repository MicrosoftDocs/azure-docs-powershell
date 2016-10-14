---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Start-AzureSqlDatabaseExport

## SYNOPSIS
Starts an export operation from an Azure SQL Database to Blob storage.

## SYNTAX

### ByContainerObject
```
Start-AzureSqlDatabaseExport [-SqlConnectionContext] <ISqlServerConnectionInformation>
 [-StorageContainer] <AzureStorageContainer> [-DatabaseName] <String> [-BlobName] <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByContainerName
```
Start-AzureSqlDatabaseExport [-SqlConnectionContext] <ISqlServerConnectionInformation>
 [-StorageContext] <AzureStorageContext> [-StorageContainerName] <String> [-DatabaseName] <String>
 [-BlobName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSqlDatabaseExport** cmdlet starts an export operation from an Azure SQL Database to Blob storage.
The operation requires a database server connection context.
Use the Get-AzureSqlDatabaseImportExportStatus cmdlet to get the status of the export operation.

## EXAMPLES

### Example 1: Export a database
```
PS C:\>$Credential = Get-Credential
PS C:\> $SqlContext = New-AzureSqlDatabaseServerContext -ServerName $ServerName -Credentials $Credential
PS C:\> $StorageContext = New-AzureStorageContext -StorageAccountName $StorageName -StorageAccountKey $StorageKey
PS C:\> $Container = Get-AzureStorageContainer -Name $ContainerName -Context $StorageContext
PS C:\> $exportRequest = Start-AzureSqlDatabaseExport -SqlConnectionContext $SqlContext -StorageContainer $Container -DatabaseName $DatabaseName -BlobName $BlobName
```

This example initiates an export process from the Azure SQL Database that has the name stored in the $DatabaseName variable to the Blob storage stored in the $BlobName variable.

## PARAMETERS

### -SqlConnectionContext
Specifies the connection context of a server that contains the database.

```yaml
Type: ISqlServerConnectionInformation
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainer
Specifies the storage container that contains the Blob into which this cmdlet export a database.

```yaml
Type: AzureStorageContainer
Parameter Sets: ByContainerObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database from which this cmdlet exports data.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobName
Specifies the name of the Azure Blob storage into which this cmdlet exports the database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContext
Specifies the context of the Blob storage container.

```yaml
Type: AzureStorageContext
Parameter Sets: ByContainerName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainerName
Specifies the name of the storage container that contains the Blob into which this cmdlet exports a database.

```yaml
Type: String
Parameter Sets: ByContainerName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.ImportExportRequest

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Export Database](https://msdn.microsoft.com/en-us/library/azure/dn781282.aspx)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseImportExportStatus](.\Get-AzureSqlDatabaseImportExportStatus.md)

[Start-AzureSqlDatabaseImport](.\Start-AzureSqlDatabaseImport.md)

