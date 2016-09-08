---
external help file: RMAzure_Automation.xml
online version: 16207dee-029f-4659-ab6f-f636f869b82b
schema: 2.0.0
---

# Remove-AzureRmAutomationDscNodeConfiguration
## SYNOPSIS
Removes metadata from DSC node configurations in Automation.

## SYNTAX

```
Remove-AzureRmAutomationDscNodeConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Force] [-IgnoreNodeMappings] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationDscNodeConfiguration** cmdlet removes metadata from APS Desired State Configuration (DSC) node configurations in azure_2 Automation.
Automation stores DSC node configuration as a Managed Object Format (MOF) configuration document.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account that contains the DSC node configurations for which this cmdlet removes metadata.

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

### -Force
ps_force

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreNodeMappings
Indicates that this cmdlet ignores node mappings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the DSC node configuration for which this cmdlet removes metadata.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NodeConfigurationName

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet removes metadata for DSC node configurations in the resource group that this parameter specifies.

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

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationDscNodeConfiguration](16207dee-029f-4659-ab6f-f636f869b82b)

[Import-AzureRmAutomationDscNodeConfiguration](0ef99c72-89fd-478d-850e-50ed5a0aba17)

[Azure Automation Cmdlets](e3d89134-0c83-4dbf-8072-062bc6f843a6)

