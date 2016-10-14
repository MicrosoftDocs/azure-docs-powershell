---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\New-AzureAutomationAccount.md
schema: 2.0.0
---

# Get-AzureAutomationAccount

## SYNOPSIS
Gets Automation accounts in a resource group.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationAccount [[-ResourceGroupName] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByAutomationAccountName
```
Get-AzureAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationAccount** cmdlet gets Azure Automation accounts in a resource group.

For more information about Automation accounts, type `Get-Help New-AzureAutomationAccount`.

## EXAMPLES

### Example 1: Get all accounts
```
PS C:\>Get-AzureAutomationAccount -ResourceGroupName "MyResourceGroup" -Name "MyAutomationAccount"
```

This command gets all Automation accounts in the resource group named MyResourceGroup.

### Example 2: Get an account
```
PS C:\>Get-AzureAutomationAccount -ResourceGroupName "MyResourceGroup" -Name "MyAutomationAccount"
```

This command gets the Automation account named MyAutomationAccount in the resource group named MyResourceGroup.

## PARAMETERS

### -Name
Specifies the name of the Automation account that this cmdlet gets.

```yaml
Type: String
Parameter Sets: ByAutomationAccountName
Aliases: AutomationAccountName

Required: True
Position: 2
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

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet gets Automation accounts.```yaml
Type: String
Parameter Sets: ByAll
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByAutomationAccountName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureAutomationAccount](.\New-AzureAutomationAccount.md)

[Remove-AzureAutomationAccount](.\Remove-AzureAutomationAccount.md)

[Set-AzureAutomationAccount](.\Set-AzureAutomationAccount.md)

