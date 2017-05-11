---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3B861550-B01D-4792-8A58-7937702A5F2A
---

# Get-AzureRmSqlServerAuditingPolicy

## SYNOPSIS
Gets the auditing policy of a SQL server.

## SYNTAX

```
Get-AzureRmSqlServerAuditingPolicy -ServerName <String> [-ResourceGroupName] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSqlServerAuditingPolicy** cmdlet gets the auditing policy of an Azure SQL server.
Specify the *ResourceGroupName*, *ServerName*, and *DatabaseName* parameters to identify the database.
This cmdlet returns a policy that is used by the Azure SQL databases that are both defined in the specified Azure SQL server and use its auditing policy.

## EXAMPLES

### Example 1: Get the auditing policy of an Azure SQL server
```
PS C:\>Get-AzureRmSqlServerAuditingPolicy -ResourceGroupName "resourcegroup01" -ServerName "server01"
ResourceGroupName  : resourcegroup01
ServerName         : server01
StorageAccountName : 
StorageKeyType     : Primary
EventType          : {PlainSQL_Success, PlainSQL_Failure, ParameterizedSQL_Success, ParameterizedSQL_Failure...} 
AuditState         : New
RetentionInDays    : 0
TableIdentifier    : Server01
```

This command gets the auditing policy of the server Server01 in resource group ResourceGroup01.

## PARAMETERS

### -ServerName
Specifies the name of the Azure SQL server for which this cmdlet gets the auditing policy.

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
Specifies the name of the resource group to which the Azure SQL server is assigned.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Security.Model.ServerAuditingPolicyModel

## NOTES

## RELATED LINKS

[Set-AzureRmSqlServerAuditingPolicy](./Set-AzureRmSqlServerAuditingPolicy.md)

[Use-AzureRmSqlServerAuditingPolicy](./Use-AzureRmSqlServerAuditingPolicy.md)




