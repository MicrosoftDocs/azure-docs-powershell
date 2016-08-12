---
external help file: RMAzure_Automation.xml
online version: 19472f94-5827-4878-a17a-d7bb10932861
schema: 2.0.0
---

# Set-AzureRmAutomationDscNode
## SYNOPSIS
Modifies the node configuration that a DSC node is mapped to.

## SYNTAX

```
Set-AzureRmAutomationDscNode [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Force]
 -Id <Guid> -NodeConfigurationName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-AzureRmAutomationDscNode** cmdlet modifies an APS Desired State Configuration (DSC) node configuration.
azure_2 Automation stores DSC node configuration as a Managed Object Format (MOF) configuration document.

## EXAMPLES

### Example 1: Modify node configuration mapping
```
PS C:\>Set-AzureRmAutomationDscNode -NodeConfigurationName "Contoso.NodeConfiguration01" -ResourceGroupName "ResourceGroup01" -Id 064a8929-c98b-25e4-80hh-111c8a6067j8
```

This command assigns the node configuration named Contoso.NodeConfiguration01 to the node that has the specified GUID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC node for which this cmdlet modifies the configuration.

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
ps_force the command to run without asking for user confirmation.

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

### -Id
Specifies the unique ID of the DSC node for which this cmdlet modifies the configuration.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: NodeId

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -NodeConfigurationName
Specifies the name of the node configuration to which this cmdlet maps the node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet modifies a DSC node configuration.

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

[Get-AzureRmAutomationDscNode](19472f94-5827-4878-a17a-d7bb10932861)

[Register-AzureRmAutomationDscNode](a6f623a1-2e69-4ea2-828b-ab63d285a009)

[Unregister-AzureRmAutomationDscNode](159d4e1d-b8db-4544-9807-c09e63fbd5dd)

