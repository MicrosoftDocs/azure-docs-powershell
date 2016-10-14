---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlServerAuditingPolicy

## SYNOPSIS
Gets the auditing policy of an Azure SQL server.

## SYNTAX

```
Get-AzureSqlServerAuditingPolicy -ServerName <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlServerAuditingPolicy cmdlet gets the auditing policy of an Azure SQL server.
Specify the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database.
This cmdlet returns a policy that is used by the Azure SQL databases that are both defined in the specified Azure SQL server and use its auditing policy.

## EXAMPLES

### Example 1: Get the auditing policy of an Azure SQL server
```
PS C:\>Get-AzureSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02"
```

This command gets the auditing policy of the server Server02 in resource group ResourceGroup11.

## PARAMETERS

### -ServerName
Specifies the name of the Azure SQL server for which this cmdlet gets an auditing policy.

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
Specifies the name of the resource group that contains the Azure SQL server.

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

[Set-AzureSqlServerAuditingPolicy]()

[Use-AzureSqlServerAuditingPolicy]()

