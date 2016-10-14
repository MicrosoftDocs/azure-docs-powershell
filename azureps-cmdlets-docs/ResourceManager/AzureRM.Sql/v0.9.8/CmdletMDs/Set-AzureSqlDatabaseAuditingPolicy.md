---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlDatabaseAuditingPolicy

## SYNOPSIS
Sets the auditing policy for an Azure SQL database.

## SYNTAX

```
Set-AzureSqlDatabaseAuditingPolicy [-PassThru] [-EventType <String[]>] [-StorageAccountName <String>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-TableIdentifier <String>] [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlDatabaseAuditingPolicy cmdlet changes the auditing policy of an Azure SQL database.
To use the cmdlet, use the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database.
Specify the StorageAccountName parameter to specify the storage account to be used for the audit logs and the StorageKeyType parameter to define which of that storage keys to use.

You can also define retention for the audit logs table by setting the value of the RetentionInDays and TableIdentifier parameters to define the period and the seed for the names of the audit logs tables.
Specify the EventType parameter to define which event types to audit.

After the cmdlet runs successfully, auditing of the database is enabled.
If the database used the policy of its server for auditing before you ran this cmdlet, auditing stops using the policy of its server.
If the cmdlet succeeds and you use the PassThru parameter, it returns an object describing the current auditing policy, as well as the database identifiers.
Database identifiers include, but are not limited to, ResourceGroupName, ServerName, and DatabaseName.

## EXAMPLES

### Example 1: Set the auditing policy of a database
```
PS C:\>Set-AzureSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01"  ¢â‚¬"StorageAccountName "Storage31"
```

This command sets the auditing policy of database named Database01 located in Server02 to use the storage account named Storage31.

### Example 2: Set the storage account key of an existing auditing policy of a database
```
PS C:\>Set-AzureSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01"  ¢â‚¬"StorageAccountKey Secondary
```

This command sets the auditing policy of database named Database01 located in Server02 to keep using the same storage account name, but use the secondary key.

### Example 3: Set the auditing policy of a database to use a specific event type
```
PS C:\>Set-AzureSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -DatabaseName "Database01"  ¢â‚¬"EventType Login_Failure
```

This command sets the auditing policy of database named Database01 located in Server02 to log the Login_Failure event type.
The command does not change the storage settings.

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
If you specify All or None at the same time, the cmdlet fails to run.

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
Wildcards are not permitted.
This parameter is not required.
When this parameter is not provided, the cmdlet will use the storage account that was defined previously as part of the auditing policy of the database.
If this is the first time a database auditing policy is defined and this parameter is not provided, the cmdlet will fail.

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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database.

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

### None

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Security.Model.DatabaseAuditingPolicyModel

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabaseAuditingPolicy]()

[Remove-AzureSqlDatabaseAuditing]()

[Azure SQL Database]()

