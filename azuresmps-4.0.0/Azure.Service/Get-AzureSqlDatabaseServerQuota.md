---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 6723557D-8052-4BFA-872C-384B1423B3AE
online version: 
schema: 2.0.0
---

# Get-AzureSqlDatabaseServerQuota

## SYNOPSIS
Gets quota information for an Azure SQL Database server.

## SYNTAX

### ByConnectionContext
```
Get-AzureSqlDatabaseServerQuota -ConnectionContext <IServerDataServiceContext> [-QuotaName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabaseServerQuota -ServerName <String> [-QuotaName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseServerQuota** cmdlet gets the quota information for a specified instance of Azure SQL Database Server.
Specify a connection context or the server name.
If you do not specify a quota name, this cmdlet gets all the quota information for the server.

## EXAMPLES

### Example 1: Get information for a specific quota
```
PS C:\> $QuotaPremium = GetAzureSqlDatabaseServerQuota $Context -QuotaName "Premium_Databases"
```

This command gets the quota named Premium_Databases from the Azure SQL Database server specified by the connection stored in the $Context variable.

### Example 2: Get information for all quotas
```
PS C:\> $QuotaList = GetAzureSqlDatabaseServerQuota $Context
```

This command gets all quota values from the server specified by the connection $Context.

## PARAMETERS

### -ConnectionContext
Specifies the connection context of a server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -QuotaName
Specifies the name of the quota value that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of a server.

```yaml
Type: String
Parameter Sets: ByServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServerQuota[]

## NOTES
* Authentication: This cmdlet can use either SQL Server authentication or certificate-based authentication. For examples of setting up authentication, see the New-AzureSqlDatabaseServerContext cmdlet.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


