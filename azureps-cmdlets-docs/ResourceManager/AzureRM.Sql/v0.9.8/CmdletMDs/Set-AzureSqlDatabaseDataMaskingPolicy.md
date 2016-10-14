---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlDatabaseDataMaskingPolicy

## SYNOPSIS
Sets data masking for an Azure SQL database.

## SYNTAX

```
Set-AzureSqlDatabaseDataMaskingPolicy [-PassThru] [-PrivilegedLogins <String>] [-DataMaskingState <String>]
 [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlDatabaseDataMaskingPolicy cmdlet sets the data masking policy for an Azure SQL database.
To use this cmdlet, use the ResourceGroupName, ServerName, and DatabaseName parameters to identify the database.
You can set the DataMaskingState parameter to specify whether data masking operations are enabled or disabled.
You can also set the PrivilegedLogins parameter to specify which users are allowed to see the unmasked data.
If the cmdlet succeeds and the PassThru parameter is used, it returns an object describing the current data masking policy as well as the database identifiers.
Database identifiers include, but are not limited to, ResourceGroupName, ServerName, and DatabaseName.

## EXAMPLES

### Example 1: Set the data masking policy for a database
```
PS C:\>Set-AzureSqlDatabaseDataMaskingPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database03"
```

This command sets the data masking policy from database named Database03 on the server named Server01.

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

### -PrivilegedLogins
Specifies a semicolon separated list of privileged user ids that can view the masking data.

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

### -DataMaskingState
Specifies whether data masking operation is enabled or disabled.
Valid values are: 
- Enabled
- Disabled

The default value is Enabled.

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
Specifies the name of the server containing the database.

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
Specifies the name of the resource group containing the database.

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

### Microsoft.Azure.Commands.Sql.Security.Model.DatabaseDataMaskingPolicyModel

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabaseDataMaskingPolicy]()

[Get-AzureSqlDatabaseDataMaskingRule]()

[New-AzureSqlDatabaseDataMaskingRule]()

[Remove-AzureSqlDatabaseDataMaskingRule]()

[Set-AzureSqlDatabaseDataMaskingRule]()

[Azure SQL Database]()

