---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Export-AzureAutomationDscConfiguration.md
schema: 2.0.0
---

# Get-AzureAutomationDscConfiguration

## SYNOPSIS
Gets DSC configurations from Automation.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationDscConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByConfigurationName
```
Get-AzureAutomationDscConfiguration [-Name] <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationDscConfiguration** cmdlet gets PowerShell Desired State Configuration (DSC) configurations from Azure Automation.

## EXAMPLES

### Example 1: Get all DSC configurations
```
PS C:\>Get-AzureAutomationDscConfiguration -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
```

This command gets metadata on all DSC configurations in the Automation account named Contoso17.

### Example 2: Get a DSC configuration by name
```
PS C:\>Get-AzureAutomationDscConfiguration -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -Name "MyConfiguration"
```

This command gets metadata on a DSC configuration named MyConfiguration in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains DSC configurations that this cmdlet gets.

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
Specifies the name of the DSC configuration that this cmdlet gets.

```yaml
Type: String
Parameter Sets: ByConfigurationName
Aliases: ConfigurationName

Required: True
Position: 3
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
Specifies the name of a resource group for which this cmdlet gets DSC configurations.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-AzureAutomationDscConfiguration](.\Export-AzureAutomationDscConfiguration.md)

[Import-AzureAutomationDscConfiguration](.\Import-AzureAutomationDscConfiguration.md)

