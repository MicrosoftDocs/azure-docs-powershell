---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: https://azure.microsoft.com/en-us/services/sql-database/
schema: 2.0.0
---

# Set-AzureSqlDatabaseServer

## SYNOPSIS
Modifies the properties of an Azure SQL Database server.

## SYNTAX

```
Set-AzureSqlDatabaseServer [-ServerName] <String> -AdminPassword <String> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlDatabaseServer** cmdlet modifies the properties of the specified instance of Azure SQL Database Server.
In the current release, you can only update the administrator account password for a server.

## EXAMPLES

### Example 1: Change the password for a server
```
PS C:\>Set-AzureSqlDatabaseServer -ServerName "lpqd0zbr8y" -AdminPassword "NewPassword"
```

This command changes the administrator account password for the Azure SQL Database server named lpqd0zbr8y.

## PARAMETERS

### -ServerName
Specifies the name of the server that this cmdlet modifies.
Specify the server name, not the fully qualified DNS name.

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

### -AdminPassword
Specifies the administrator account password for the Azure SQL Database server.
You must specify a strong password.
For more information, see Strong Passwordshttp://go.microsoft.com/fwlink/p/?LinkId=154152 (http://go.microsoft.com/fwlink/p/?LinkId=154152) at the Microsoft Developer Network.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## OUTPUTS

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseServer](.\Get-AzureSqlDatabaseServer.md)

[New-AzureSqlDatabaseServer](.\New-AzureSqlDatabaseServer.md)

[Remove-AzureSqlDatabaseServer](.\Remove-AzureSqlDatabaseServer.md)

