---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Set-AzureSqlDatabase

## SYNOPSIS
Sets properties for an Azure SQL Database.

## SYNTAX

### ByNameWithConnectionContext
```
Set-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-DatabaseName] <String>
 [-NewDatabaseName <String>] [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByObjectWithConnectionContext
```
Set-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-Database] <Database>
 [-NewDatabaseName <String>] [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByObjectWithServerName
```
Set-AzureSqlDatabase [-ServerName] <String> [-Database] <Database> [-NewDatabaseName <String>]
 [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByNameWithServerName
```
Set-AzureSqlDatabase [-ServerName] <String> [-DatabaseName] <String> [-NewDatabaseName <String>]
 [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlDatabase** cmdlet sets properties for an Azure SQL Database.
You can specify the database by name, or pass an Azure SQL Database object through the pipeline.
You can specify the server by name, or pass an Azure SQL Database server connection context.
Create a connection context by running the New-AzureSqlDatabaseServerContext cmdlet.
If you specify the server by name, the cmdlet uses the current Azure subscription information to authenticate the request.

## EXAMPLES

### Example 1: Change the size of a database by using a connection context
```
PS C:\>$Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ConnectionContext $Context -Database $Database01 -MaxSizeGB 20
```

This example changes the size of the database named Database01 to 20 GB, in the Azure SQL Database server connection context $Context.

### Example 2: Change the size of a database by using a server name
```
PS C:\>$Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ServerName "lpqd0zbr8y" -Database $Database01 -MaxSizeGB 20
```

This example changes the size of the database named Database01 to 20 GB in the server named lpqd0zbr8y.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByNameWithConnectionContext, ByObjectWithConnectionContext
Aliases: Context

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Database
Specifies an object that represents the Azure SQL Database that this cmdlet modifies.

```yaml
Type: Database
Parameter Sets: ByObjectWithConnectionContext, ByObjectWithServerName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewDatabaseName
Specifies the new name of the database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edition
Specifies the new edition for the Azure SQL Database.
Valid values are: 

- None
- Web
- Business
- Basic
- Standard
-  Premium

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

### -MaxSizeGB
Specifies the new maximum size for the database in gigabytes.
You can specify either this parameter or the *MaxSizeBytes* parameter.
The acceptable values differ based on edition.

Basic Edition values: 1 or 2

Standard Edition values: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, or 250

Premium Edition values: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, 250, 300, 400, or 500

Web Edition values: 1 or 5

Business Edition values: 10, 20, 30, 40, 50, 100, or 150

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

### -MaxSizeBytes
Specifies the new maximum size for the database in bytes.
You can specify either this parameter or the *MaxSizeGB* parameter.
See the *MaxSizeGB* parameter for acceptable values based on edition.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceObjective
Specifies an object representing the new service objective (performance level) for this database.
Valid values are: 

- Basic: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
- Standard (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
- Standard (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
- Standard (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
- *Standard (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
- Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

*Standard (S3) is part of the Latest SQL Database Update V12 (preview).
For more information, see What's New in the Azure SQL Database V12 Previewhttp://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/.

```yaml
Type: ServiceObjective
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns the updated Azure SQL Database.

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

### -Force
Allows the action to complete without prompting you for confirmation.

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

### -Sync
@{Text=}

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: ByNameWithConnectionContext, ByNameWithServerName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that contains the database that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: ByObjectWithServerName, ByNameWithServerName
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Update Database](https://msdn.microsoft.com/en-us/library/azure/dn505718.aspx)

[Get-AzureSqlDatabase](.\Get-AzureSqlDatabase.md)

[New-AzureSqlDatabase](.\New-AzureSqlDatabase.md)

[Remove-AzureSqlDatabase](.\Remove-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](.\New-AzureSqlDatabaseServerContext.md)

