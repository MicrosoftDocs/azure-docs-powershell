---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: .\Get-AzureAutomationVariable.md
schema: 2.0.0
---

# New-AzureAutomationVariable

## SYNOPSIS
Creates an Azure Automation variable.

## SYNTAX

```
New-AzureAutomationVariable [-Name] <String> -Encrypted <Boolean> [-Description <String>] [-Value <Object>]
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureAutomationVariable** cmdlet creates a variable in Microsoft Azure Automation.

## EXAMPLES

### Example 1: Create a new variable with a simple value
```
PS C:\> New-AzureAutomationVariable -AutomationAccountName "Contoso17" -Name "MyStringVariable" -Encrypted $false -Value "My String"
```

This command creates a new variable named MyStringVariable with a string value in the Azure Automation account named Contoso17.

### Example 2: Create a new variable with a complex value
```
PS C:\> $vm = Get-AzureVM -ServiceName "MyVM" -Name "MyVM"
PS C:\> New-AzureAutomationVariable -AutomationAccountName "Contoso17" -Name "MyComplexVariable" -Encrypted $false -Value $vm
```

These commands create a new variable called MyComplexVariable in the Azure Automation account named Contoso17. 
A complex object is used for its value, in this case a virtual machine object.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the automation account the variable will be stored in.

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

### -Description
Specifies a description for the variable.

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

### -Encrypted
Specifies whether the value of the variable should be stored encrypted.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the variable.

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

### -Value
Specifies a value to store in the variable.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-AzureAutomationVariable](.\Get-AzureAutomationVariable.md)

[Set-AzureAutomationVariable](.\Set-AzureAutomationVariable.md)

[Remove-AzureAutomationVariable](.\Remove-AzureAutomationVariable.md)

