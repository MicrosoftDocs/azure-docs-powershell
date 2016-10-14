---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: .\Get-AzureSqlDatabase.md
schema: 2.0.0
---

# New-AzureSqlDatabase

## SYNOPSIS
Creates an Azure SQL Database.

## SYNTAX

### ByConnectionContext
```
New-AzureSqlDatabase [-ConnectionContext] <IServerDataServiceContext> [-DatabaseName] <String>
 [-Collation <String>] [-Edition <DatabaseEdition>] [-ServiceObjective <ServiceObjective>] [-MaxSizeGB <Int32>]
 [-MaxSizeBytes <Int64>] [-Force] [-Profile <AzureProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByServerName
```
New-AzureSqlDatabase [-ServerName] <String> [-DatabaseName] <String> [-Collation <String>]
 [-Edition <DatabaseEdition>] [-ServiceObjective <ServiceObjective>] [-MaxSizeGB <Int32>]
 [-MaxSizeBytes <Int64>] [-Force] [-Profile <AzureProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlDatabase** cmdlet creates an Azure SQL Database.
You can specify the server by using an Azure SQL Database server connection context that you create using the **New-AzureSqlDatabaseServerContext** cmdlet.
Or, if you specify the server name, the cmdlet uses the current Azure subscription information to authenticate the request to access the server.

When you create a new database by specifying an Azure SQL Database server, the **New-AzureSqlDatabase** cmdlet creates a temporary connection context using the specified server name and the current Azure subscription information to perform the operation.

## EXAMPLES

### Example 1: Create a database
```
PS C:\>$Database01 = New-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01" -Edition "Business" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

This command creates an Azure SQL Database named Database1, for the Azure SQL Database server connection context $Context.

### Example 2: Create a database in the current subscription
```
PS C:\>$Database01 = New-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01" -Edition "Business" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

This example creates a database named Database1, in the specified Azure SQL Database server named lpqd0zbr8y.
The cmdlet uses the current Azure subscription information to authenticate the request to access the server.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server where this cmdlet creates a database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the new database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Collation
Specifies a collation for the new database.

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

### -Edition
Specifies the edition for the new Azure SQL Database.
Valid values are: Web, Business, Basic, Standard, or Premium.
The default value is Web.

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

### -ServiceObjective
Specifies an object that represent the new service objective (performance level) for this database.
This value represents the level of resources assigned to this database.
Valid values are: 

Basic: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
Standard (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
Standard (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
Standard (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
*Standard (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

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

### -MaxSizeGB
Specifies the maximum size of the database in gigabytes.
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
Specifies the maximum size of the database in bytes.
You can specify either this parameter or the *MaxSizeGB* parameter.
See the *MaxSizeGB* parameter description for acceptable values based on edition.

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

### -Force
Allows the action to complete without prompting the user for confirmation.

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

### -ServerName
Specifies the name of the Azure SQL Database server to contain the new database.

```yaml
Type: String
Parameter Sets: ByServerName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## NOTES
* To delete a database that was created by **New-AzureSqlDatabase**, use the **Remove-AzureSqlDatabase** cmdlet.

## RELATED LINKS

[Get-AzureSqlDatabase](.\Get-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](.\New-AzureSqlDatabaseServerContext.md)

[Remove-AzureSqlDatabase](.\Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](.\Set-AzureSqlDatabase.md)

