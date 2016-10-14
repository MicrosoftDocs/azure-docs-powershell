---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationAccount.md
schema: 2.0.0
---

# New-AzureAutomationAccount

## SYNOPSIS
Creates an Automation account.

## SYNTAX

```
New-AzureAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Plan <String>]
 [-Tags <IDictionary>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureAutomationAccount** cmdlet creates an Azure Automation account in a resource group.

An Automation account is a container for Automation resources that is isolated from the resources of other Automation accounts.
Automation resources include runbooks, DSC configurations, jobs, and assets.

## EXAMPLES

### Example 1: Create an automation account
```
PS C:\> New-AzureAutomationAccount -Name "MyAutomationAccount" -Location "East US" -ResourceGroupName "ResourceGroup01"
```

This command creates a new automation account named MyAutomationAccount in the East US region.

## PARAMETERS

### -Location
Specifies the location in which this cmdlet creates the Automation account.
To obtain valid locations, use the **Get-AzureLocation** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the Automation account.

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

### -Plan
Specifies the plan for the Automation account. Valid values are: Basic and Free.```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Free, Basic

Required: False
Position: Named
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
Specifies the name of a resource group to which this cmdlet adds an Automation account.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
Specifies tags for the Automation account.```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
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

[Remove-AzureAutomationAccount](.\Remove-AzureAutomationAccount.md)

[Set-AzureAutomationAccount](.\Set-AzureAutomationAccount.md)

