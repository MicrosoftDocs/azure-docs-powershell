---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureSqlDatabaseDataMaskingRule

## SYNOPSIS
Sets the properties of a data masking rule in an Azure SQL database.

## SYNTAX

```
Set-AzureSqlDatabaseDataMaskingRule [-ColumnName <String>] [-TableName <String>] [-SchemaName <String>]
 [-MaskingFunction <String>] [-PrefixSize <UInt32>] [-ReplacementString <String>] [-SuffixSize <UInt32>]
 [-NumberFrom <Double>] [-NumberTo <Double>] [-PassThru] -RuleId <String> [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureSqlDatabaseDataMaskingRule cmdlet is used to set a data masking rule in an Azure SQL database.
To use the cmdlet, provide the ResourceGroupName, ServerName, DatabaseName, and RuleId parameters to identify the rule.
You can provide any of the parameters of SchemaName, TableName, and ColumnName to retarget the rule.
Specify the MaskingFunction parameter to modify how the data is masked.
If you specify a value of Number or Text for MaskingFunction, you can specify the NumberFrom and NumberTo parameters for number masking or the PrefixSize, ReplacementString, and SuffixSize parameters for text masking.
If the command succeeds, and if you specify the PassThru parameter, the cmdlet returns an object that describe the data masking rule properties, and the rule identifiers.
Rule identifiers include, but are not limited to, ResourceGroupName, ServerName,DatabaseName and RuleId.

## EXAMPLES

### Example 1: Change the range of a data masking rule in a database
```
PS C:\>Set-AzureSqlDatabaseDataMaskingRule -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database03"  ¢â‚¬"RuleId "Rule17"  ¢â‚¬"NumberFrom 23  ¢â‚¬"NumberTo 42
```

This command modifies a data masking rule that has the ID Rule17.
That rule operates in the database named Database03 on server Server01.
This command changes the boundaries for the interval in which a random number is generated as the masked value.
The new range is between 23 and 42.

## PARAMETERS

### -MaskingFunction
Specifies the masking function that the rule uses.
Valid values are: 

- Default
- NoMasking
- Text
- Number
- SocialSecurityNumber
- CreditCardNumber
- Email

The default value is Default.

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

### -TableName
Specifies the name of the table in the database of which the masked column is part.

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

### -ColumnName
Specifies the name of the column that is the target of this masking rule.

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

### -PrefixSize
Specifies the number of characters in the beginning of the text that is not masked.
Specify this parameter only if you specify a value of Text for the MaskingFunction parameter.
The default value is 0.

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

### -ReplacementString
Specifies the number of characters in the end of the text that is not masked.
Specify this parameter only if you specify a value of Text for the MaskingFunction parameter.
The default value is 0.

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

### -SuffixSize
Specifies the number of characters in the end of the text that is not masked.
Specify this parameter only if you specify a value of Text for the MaskingFunction parameter.
The default value is 0.

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

### -NumberFrom
Specifies the lower bound number of the interval from which a random value is selected.
Specify this parameter only if you specify a value of Number for the MaskingFunction parameter.
The default value is 0.

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberTo
Specifies the upper bound number of the interval from which a random value is selected.
Specify this parameter only if you specify a value of Number for the MaskingFunction parameter.
The default value is 0.

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -RuleId
Specifies the identifier for the data masking rule.

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

### -SchemaName
@{Text=}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Security.Model.DatabaseDataMaskingRuleModel

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlDatabaseDataMaskingRule]()

[New-AzureSqlDatabaseDataMaskingRule]()

[Remove-AzureSqlDatabaseDataMaskingRule]()

[Azure SQL Database]()

