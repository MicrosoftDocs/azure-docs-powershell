---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationAccount.md
schema: 2.0.0
---

# Remove-AzureAutomationAccount

## SYNOPSIS
Removes an Automation account.

## SYNTAX

```
Remove-AzureAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureAutomationAccount** cmdlet removes an Azure Automation account from a resource group.

For more information about Automation accounts, type `Get-Help New-AzureAutomationAccount`.

## EXAMPLES

### Example 1: Remove an automation account
```
PS C:\>Remove-AzureAutomationAccount -Name "MyAutomationAccount" -Force -ResourceGroupName "ResourceGroup01"
```

This command removes an automation account named MyAutomationAccount without prompting for user validation.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Specifies the name of the Automation account that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
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
Specifies the name of the resource group from which this cmdlet removes an Automation account.```yaml
Type: String
Parameter Sets: (All)
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

[Get-AzureAutomationAccount](.\Get-AzureAutomationAccount.md)

[New-AzureAutomationAccount](.\New-AzureAutomationAccount.md)

[Set-AzureAutomationAccount](.\Set-AzureAutomationAccount.md)

