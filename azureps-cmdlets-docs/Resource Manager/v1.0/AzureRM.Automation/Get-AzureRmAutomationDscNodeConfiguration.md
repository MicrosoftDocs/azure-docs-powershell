---
external help file: RMAzure_Automation.xml
online version: 0ef99c72-89fd-478d-850e-50ed5a0aba17
schema: 2.0.0
---

# Get-AzureRmAutomationDscNodeConfiguration
## SYNOPSIS
Gets metadata for DSC node configurations in Automation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRmAutomationDscNodeConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-RollupStatus]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRmAutomationDscNodeConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -Name <String>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRmAutomationDscNodeConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-RollupStatus] -ConfigurationName <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationDscNodeConfiguration** cmdlet gets metadata for APS Desired State Configuration (DSC) node configurations in azure_2 Automation.
Automation stores DSC node configuration as a Managed Object Format (MOF) configuration document.

## EXAMPLES

### Example 1: Get all DSC node configurations
```
PS C:\>Get-AzureRmAutomationDscNodeConfiguration -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17"
```

This command gets metadata for all DSC node configurations in the Automation account named Contoso17.

### Example 2: Get all DSC node configurations for a DSC configuration
```
PS C:\>Get-AzureRmAutomationDscNodeConfiguration -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -ConfigurationName "ContosoConfiguration"
```

This command gets metadata for all DSC node configurations in the Automation account named Contoso17 that the DSC configuration named ContosoConfiguration generated.

### Example 3: Get a DSC node configuration by name
```
PS C:\>Get-AzureRmAutomationDscNodeConfiguration -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "ContosoConfiguration.webserver"
```

This command gets metadata for a DSC node configuration with the name ContosoConfiguration.webserver in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account that contains the DSC node configurations for which this cmdlet gets metadata.

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

### -ConfigurationName
Specifies the name of DSC configuration for which this cmdlet gets node configuration metadata.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the DSC node configuration for which this cmdlet gets metadata.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: NodeConfigurationName

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet gets metadata for DSC node configurations in the resource group that this parameter specifies.

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

### -RollupStatus
Specifies the rollup status of DSC node configurations that this cmdlet gets.
Valid values are: 

-- Bad 
-- Good

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 
Accepted values: Good, Bad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-AzureRmAutomationDscNodeConfiguration](0ef99c72-89fd-478d-850e-50ed5a0aba17)

