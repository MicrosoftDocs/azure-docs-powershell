---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: BE00A25D-3ECE-4B27-9D79-78128CFEBDB0
online version: 
schema: 2.0.0
---

# Get-AzureSqlDatabaseServerFirewallRule

## SYNOPSIS
Gets firewall rules for Azure SQL Database Server.

## SYNTAX

```
Get-AzureSqlDatabaseServerFirewallRule -ServerName <String> [-RuleName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlDatabaseServerFirewallRule** cmdlet gets firewall rules for an instance of Azure SQL Database Server.
If you specify a firewall rule by name, this cmdlet returns information about that firewall rule.
Otherwise, the cmdlet returns information about all the firewall rules on the specified Azure SQL Database server.

## EXAMPLES

### Example 1: Get all firewall rules on a server
```
PS C:\> Get-AzureSqlDatabaseServerFirewallRule -ServerName "lpqd0zbr8y"
```

This command gets all the firewall rules on the Azure SQL Database server named lpqd0zbr8y.

### Example 2: Get a firewall rule by using its name
```
PS C:\> Get-AzureSqlDatabaseServerFirewallRule -ServerName "lpqd0zbr8y" -RuleName "FirewallRule24"
```

This command gets the firewall rule named FirewallRule24 on the server named lpqd0zbr8y.

## PARAMETERS

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

### -RuleName
Specifies the name of the firewall rule that this cmdlet gets.

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
This cmdlet gets firewall rules from the server that this parameter specifies.
Specify the server name, not the fully qualified DNS name.

```yaml
Type: String
Parameter Sets: (All)
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerFirewallRuleContext

## OUTPUTS

### IEnumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerFirewallRuleContext\>

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[List Firewall Rules](https://msdn.microsoft.com/en-us/library/azure/dn505715.aspx)

[Operations for Azure SQL Databases](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabaseServerFirewallRule](./New-AzureSqlDatabaseServerFirewallRule.md)

[Remove-AzureSqlDatabaseServerFirewallRule](./Remove-AzureSqlDatabaseServerFirewallRule.md)

[Set-AzureSqlDatabaseServerFirewallRule](./Set-AzureSqlDatabaseServerFirewallRule.md)


