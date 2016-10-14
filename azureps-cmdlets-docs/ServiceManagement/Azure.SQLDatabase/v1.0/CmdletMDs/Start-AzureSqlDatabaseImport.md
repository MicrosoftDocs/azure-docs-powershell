---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Start-AzureSqlDatabaseImport

## SYNOPSIS
Starts an import operation from blob storage to an ssSDS.

## SYNTAX

### ByContainerObject
```
Start-AzureSqlDatabaseImport [-SqlConnectionContext] <ISqlServerConnectionInformation>
 [-StorageContainer] <AzureStorageContainer> [-DatabaseName] <String> [-BlobName] <String>
 [-Edition <DatabaseEdition>] [-DatabaseMaxSize <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByContainerName
```
Start-AzureSqlDatabaseImport [-SqlConnectionContext] <ISqlServerConnectionInformation>
 [-StorageContext] <AzureStorageContext> [-StorageContainerName] <String> [-DatabaseName] <String>
 [-BlobName] <String> [-Edition <DatabaseEdition>] [-DatabaseMaxSize <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSqlDatabaseImport** cmdlet starts an import operation from azure_2 Blob storage to an ssSDS.
If the database does not exist, this cmdlet creates it by using the size and edition values that you specify.
The operation requires a database server connection context.
Use the Get-AzureSqlDatabaseImportExportStatus cmdlet to get the status of the import operation.

## EXAMPLES

### Example 1: Import a database
```
PS C:\>$Credential = Get-Credential
PS C:\> $SqlContext = New-AzureSqlDatabaseServerContext -ServerName $ServerName -Credentials $Credential
PS C:\> $StorageContext = New-AzureStorageContext -StorageAccountName $StorageName -StorageAccountKey $StorageKey
PS C:\> $Container = Get-AzureStorageContainer -Name $ContainerName -Context $StorageContext
PS C:\> $ImportRequest = Start-AzureSqlDatabaseImport -SqlConnectionContext $SqlContext -StorageContainer $Container -DatabaseName $DatabaseName -BlobName $BlobName
```

This example initiates an import process from the Blob storage in the $BlobName variable into the ssSDS named DatabaseName.

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
Specifies the storage container that contains the Blob from which this cmdlet imports a database.

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
Specifies a name for the database.
If the database does not exist, this cmdlet creates it, and assigns the name that this parameter specifies.

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
Specifies the name of the azure_2 Blob storage from which this cmdlet imports the database.

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

### -Edition
Specifies the edition of the database.
If the database does not exist, this cmdlet creates it as this edition.
Valid values are: 

- None
- Web 
- Business 
- Basic
- Standard
- Premium

The default is Web.

```yaml
Type: DatabaseEdition
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseMaxSize
Specifies the maximum size, in gigabytes, for the database.
If the database does not exist, this cmdlet creates it based on this maximum size.
The acceptable values differ based on edition.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
Specifies the name of the Blob storage container.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.ImportExportRequest

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Import Database](https://msdn.microsoft.com/en-us/library/azure/dn781284.aspx)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseImportExportStatus](.\Get-AzureSqlDatabaseImportExportStatus.md)

[Start-AzureSqlDatabaseExport](.\Start-AzureSqlDatabaseExport.md)

