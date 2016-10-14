---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureSqlServerAuditing

## SYNOPSIS
Removes auditing of an Azure SQL server.

## SYNTAX

```
Remove-AzureSqlServerAuditing [-PassThru] -ServerName <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureSqlServerAuditing** cmdlet removes the auditing of an Azure SQL server.
To use this cmdlet, specify the ResourceGroupName and ServerName parameters to identify the server.
After you run this cmdlet, auditing of the databases in the provided Azure SQL server, that are defined as using this policy of that Azure SQL server, is not performed.
If the command succeeds, and you specify the PassThru parameter, the cmdlet returns an object that describes the current auditing policy and the Azure SQL server identifiers.
Server identifiers include the ResourceGroupName and ServerName.

## EXAMPLES

### Example 1: Remove the auditing of an Azure SQL server
```
PS C:\>Remove-AzureSqlDatabaseAuditing -ResourceGroupName "ResourceGroup11" -ServerName "Server02"
```

This command removes the auditing of all the databases located in Server02 in resource group ResourceGroup11 that use the policy of that server.

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ServerName
Specifies the name of the Azure SQL server.

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

### -ResourceGroupName
Specifies the name of the resource group of the Azure SQL server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSqlDatabaseAuditingPolicy]()

[Set-AzureSqlDatabaseAuditingPolicy]()

