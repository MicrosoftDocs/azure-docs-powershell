---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureSqlDatabaseDataMaskingRule

## SYNOPSIS
Creates a data masking rule for an Azure SQL database.

## SYNTAX

```
New-AzureSqlDatabaseDataMaskingRule -ColumnName <String> -SchemaName <String> -TableName <String>
 -MaskingFunction <String> [-PrefixSize <UInt32>] [-ReplacementString <String>] [-SuffixSize <UInt32>]
 [-NumberFrom <Double>] [-NumberTo <Double>] [-PassThru] -RuleId <String> [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlDatabaseDataMaskingRule** cmdlet is used to create a data masking rule in an Azure SQL database.
To use the cmdlet, use the *ResourceGroupName*, *ServerName*, *DatabaseName*, and *RuleId* parameters to identify the rule.
Provide the *TableName* and *ColumnName* to specify the target of the rule and the *MaskingFunction* parameter to define how the data is masked.

If *MaskingFunction* has a value of Number or Text, you can specify the *NumberFrom* and *NumberTo* parameters, for number masking, or the *PrefixSize*, *ReplacementString*, and *SuffixSize* for text masking.

If the command succeeds and the *PassThru* parameter is used, the cmdlet returns an object describing the data masking rule properties as well as the rule identifiers.
Rule identifiers include, but are not limited to, **ResourceGroupName**, **ServerName**, **DatabaseName**, and **RuleID**.

## EXAMPLES

### Example 1: Create a data masking rule for a number column in a database
```
PS C:\>Set-AzureSqlDatabaseDataMaskingRule -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database03"  ¢â‚¬"RuleId "Rule17"  ¢â‚¬"SchemaName "Schema31"  ¢â‚¬"TableName "Table01"  ¢â‚¬"ColumnName "Column22"  ¢â‚¬"MaskingFunction Number  ¢â‚¬"NumberFrom 5  ¢â‚¬"NumberTo 14
```

This command creates a data masking rule for the column named Column22 in the table named Table01 in the schema named Schema31.
Database03 contains all these elements.
The rule is a number masking rule that uses a random number between 5 and 14 as the masked value.
The rule is named Rule17.

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

Required: True
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

Required: True
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

Required: True
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
The default value is an empty string.

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

Required: True
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

[Remove-AzureSqlDatabaseDataMaskingRule]()

[Set-AzureSqlDatabaseDataMaskingRule]()

[Azure SQL Database]()

