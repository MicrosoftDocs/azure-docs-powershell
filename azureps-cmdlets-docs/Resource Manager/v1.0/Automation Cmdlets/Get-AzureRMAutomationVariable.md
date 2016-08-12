---
external help file: RMAzure_Automation.xml
online version: 4103a716-9567-4836-b522-d2484452a60e
schema: 2.0.0
---

# Get-AzureRMAutomationVariable
## SYNOPSIS
Gets an Automation variable.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationVariable [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationVariable [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationVariable** cmdlet gets one or more azure_2 Automation variables.
To get a specific variable, specify its name.

## EXAMPLES

### Example 1: Get a variable
```
PS C:\>$Variable = Get-AzureRmAutomationVariable -AutomationAccountName "Contoso17" -Name "Variable06" -ResourceGroupName "ResourceGroup01"
PS C:\> $Value = $Variable.value
```

The first command gets an Automation variable named Variable06 in the account named Contoso17.
The command stores that object in the $Variable variable.

The second command uses standard dot notation to refer to the **value** property of $Variable.
The command stores the value in the $value variable.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the variables that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a variable that this cmdlet gets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group for which this cmdlet gets variables.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Variable

## NOTES

## RELATED LINKS

[New-AzureRmAutomationVariable](4103a716-9567-4836-b522-d2484452a60e)

[Remove-AzureRmAutomationVariable](c154838a-0b3d-4347-96a5-31ac572b329c)

[Set-AzureRmAutomationVariable](3bc5445e-7884-4dab-b00d-3bdfed9f05c5)

