---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: .\Get-AzureAutomationAccount.md
schema: 2.0.0
---

# New-AzureAutomationAccount

## SYNOPSIS
Creates an Automation Account.

## SYNTAX

```
New-AzureAutomationAccount [-Name] <String> [-Location] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureAutomationAccount** cmdlet creates a new automation account in Microsoft Azure Automation.

## EXAMPLES

### Example 1: Create an automation account
```
PS C:\> New-AzureAutomationAccount -Name "MyAutomationAccount" -Location "East US"
```

This command creates a new automation account named MyAutomationAccount in the East US region.

## PARAMETERS

### -Location
Specifies the name of the region for the automation account.

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

### -Name
Specifies the name of the automation account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: True
Position: 1
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

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## NOTES

## RELATED LINKS

[Get-AzureAutomationAccount](.\Get-AzureAutomationAccount.md)

[Remove-AzureAutomationAccount](.\Remove-AzureAutomationAccount.md)

