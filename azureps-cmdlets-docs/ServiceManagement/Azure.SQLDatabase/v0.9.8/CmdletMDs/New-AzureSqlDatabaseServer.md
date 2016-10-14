---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: .\Get-AzureSqlDatabaseServer.md
schema: 2.0.0
---

# New-AzureSqlDatabaseServer

## SYNOPSIS
Creates an Azure SQL Database server.

## SYNTAX

```
New-AzureSqlDatabaseServer [-AdministratorLogin] <String> -AdministratorLoginPassword <String>
 -Location <String> [-Version <Single>] [-Force] [-Profile <AzureProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlDatabaseServer** cmdlet creates an instance of Azure SQL Database Server in the current subscription.

## EXAMPLES

### Example 1: Create a server
```
PS C:\>New-AzureSqlDatabaseServer -Location "East US" -AdministratorLogin "AdminLogin" -AdministratorLoginPassword "AdminPassword"
```

This command creates a version 11 Azure SQL Database server.

### Example 2: Create a version 12 server
```
PS C:\>New-AzureSqlDatabaseServer -Location "East US" -AdministratorLogin "AdminLogin" -AdministratorLoginPassword "AdminPassword" -Version "12.0"
```

This command creates a version 12 server.

## PARAMETERS

### -AdministratorLogin
Specifies the administrator account name for the new Azure SQL Database server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdministratorLoginPassword
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

### -Location
Specifies the location of the data center where this cmdlet creates the server.
For more information, see Azure Regionshttp://azure.microsoft.com/regions/ (http://azure.microsoft.com/regions/#services).

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

### -Version
Specifies the version of the new server.
Valid values are: 2.0 and 12.0.

```yaml
Type: Single
Parameter Sets: (All)
Aliases: 

Required: False
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## NOTES

## RELATED LINKS

[Get-AzureSqlDatabaseServer](.\Get-AzureSqlDatabaseServer.md)

[Remove-AzureSqlDatabaseServer](.\Remove-AzureSqlDatabaseServer.md)

[Set-AzureSqlDatabaseServer](.\Set-AzureSqlDatabaseServer.md)

