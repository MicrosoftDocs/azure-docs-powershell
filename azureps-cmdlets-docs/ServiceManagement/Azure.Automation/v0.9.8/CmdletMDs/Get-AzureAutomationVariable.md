---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: .\New-AzureAutomationVariable.md
schema: 2.0.0
---

# Get-AzureAutomationVariable

## SYNOPSIS
Gets an Azure Automation variable.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationVariable [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureAutomationVariable [-Name] <String> [-AutomationAccountName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationVariable** cmdlet gets one or more Microsoft Azure Automation variables.
By default, all variables are returned.
To get a specific variable, specify its name.

## EXAMPLES

### Example 1: Get a variable
```
PS C:\> $variable = Get-AzureAutomationVariable -AutomationAccountName
PS C:\> "Contoso17" -Name "MyVariable"
PS C:\> $value = $variable.value
```

These commands get an Automation variable called MyVariable and assign its value to a variable called $value.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Azure Automation account with the variable.

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

### -Name
Specifies the name of a variable.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
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

### Microsoft.Azure.Commands.Automation.Model.Variable

## NOTES

## RELATED LINKS

[New-AzureAutomationVariable](.\New-AzureAutomationVariable.md)

[Set-AzureAutomationVariable](.\Set-AzureAutomationVariable.md)

[Remove-AzureAutomationVariable](.\Remove-AzureAutomationVariable.md)

