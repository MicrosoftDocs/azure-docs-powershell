---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlServerAuditingPolicy

## SYNOPSIS
Changes the auditing policy of an Azure SQL server.

## SYNTAX

```
Set-AzureSqlServerAuditingPolicy [-PassThru] [-EventType <String[]>] [-StorageAccountName <String>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-TableIdentifier <String>] -ServerName <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlServerAuditingPolicy cmdlet changes the auditing policy of an Azure SQL server.
Specify the ResourceGroupName and ServerName parameters to identify the server, the StorageAccountName parameter to specify the storage account to be used for the audit logs and the StorageKeyType parameter to define which of that storage keys to use.
You can also define retention for the audit logs table by setting the value of the RetentionInDays and TableIdentifier parameters to define the period and the seed for the names of the audit logs tables.
Specify the EventType parameter to define which event types to audit.
After you run this cmdlet, auditing of the databases that use the policy of this server is enabled.
If the cmdlet succeeds, and you specify the PassThru parameter, the cmdlet returns an object that describes the current auditing policy, and the server ¢â‚¬â"¢s identifiers.
Server identifiers include, but are not limited to, ResourceGroupName and ServerName.

## EXAMPLES

### Example 1: Set the auditing policy of an Azure SQL server
```
PS C:\>Set-AzureSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02"  ¢â‚¬"StorageAccountName "Storage22"
```

This command sets the auditing policy of the server named Server02 to use storage account named Storage22.

### Example 2: Set the storage account key of an already existing auditing policy of an Azure SQL server
```
PS C:\>Set-AzureSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02"  ¢â‚¬"StorageAccountKey Secondary
```

This command sets the auditing policy of the server named Server02 to use the secondary key.
The command does not modify the storage account name.

### Example 3: Set the auditing policy of an Azure SQL server to use a specific event type
```
PS C:\>Set-AzureSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02"  ¢â‚¬"EventType Login_Failure
```

This command sets the auditing policy of the server named Server02 to use the Login_Failure event type.
This command does not modify any other setting.

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

### -EventType
Specifies the event types to audit.
Valid values are: 

- PlainSQL_Success
- PlainSQL_Failure
- ParameterizedSQL_Success
- ParameterizedSQL_Failure
- StoredProcedure_Success
- StoredProcedure_Failure
- Login_Success
- Login_Failure 
- TransactionManagement_Success
- TransactionManagement_Failure
- All
- None

You can specify several event types.
You can specify All to audit all of the event types or None to specify that no events will be audited.
If you specify All or None at the same time, the cmdlet fails.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the storage account to be used when auditing the database.
Wildcard characters are not permitted.
If you do not specify this parameter, the cmdlet uses the storage account that was defined previously as part of the auditing policy of the database.
If this is the first time a database auditing policy is defined and you do not specify this parameter, the cmdlet fails.

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

### -StorageKeyType
Specifies which of the storage access keys to use.
Valid values are: 

- Primary
- Secondary

The default value is Primary.

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

### -RetentionInDays
Specifies the number of retention days for the audit logs table.
A value of zero (0) means that the table is not retained.
The default value is zero.
If you specify a value greater than zero, you must specify a value for the TableIdentifer parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TableIdentifier
Specifies the name of the audit logs table.
Specify this value if you specify a value greater than zero for the RetentionInDays parameter.

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
Specifies the name of the server that contains the database.

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
Specifies the name of the resource group that contains the database.

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
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlServerAuditingPolicy]()

[Use-AzureSqlServerAuditingPolicy]()

