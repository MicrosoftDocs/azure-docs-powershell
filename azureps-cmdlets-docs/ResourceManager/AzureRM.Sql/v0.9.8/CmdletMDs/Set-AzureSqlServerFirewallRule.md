---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlServerFirewallRule

## SYNOPSIS
Modifies a firewall rule in Azure SQL Database server.

## SYNTAX

```
Set-AzureSqlServerFirewallRule [-FirewallRuleName] <String> -StartIpAddress <String> -EndIpAddress <String>
 [-ServerName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlServerFirewallRule cmdlet modifies a firewall rule in Azure SQL Database server.

## EXAMPLES

### Example 1: Modify a firewall rule
```
PS C:\>Set-AzureSqlServerFirewallRule -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -FirewallRuleName "FirewallRule24" -StartIpAddress "192.168.0.197" -EndIpAddress "192.168.0.199"
```

This command modifies a firewall rule named FirewallRule24 on the server named Server01.
The command modifies the start and end IP addresses.

## PARAMETERS

### -EndIpAddress
Specifies the end value of the IP address range for this rule.

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

### -FirewallRuleName
Specifies the name of the firewall rule that this cmdlet modifies.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet modifies a firewall rule on a server in the resource group that this cmdlet specifies.

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

### -ServerName
Specifies the name of a server.
This cmdlet modifies a firewall rule on the server that this parameter specifies.

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

### -StartIpAddress
Specifies the start value of the IP address range for the firewall rule.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Azure SQL Database]()

[Get-AzureSqlServerFirewallRule]()

[New-AzureSqlServerFirewallRule]()

[Remove-AzureSqlServerFirewallRule]()

