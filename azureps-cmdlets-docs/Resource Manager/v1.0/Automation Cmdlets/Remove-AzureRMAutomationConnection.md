---
external help file: RMAzure_Automation.xml
online version: 68f56d1c-23a9-4cb5-8fe8-c3a1e7c2ac1a
schema: 2.0.0
---

# Remove-AzureRMAutomationConnection
## SYNOPSIS
Removes an Automation connection.

## SYNTAX

```
Remove-AzureRMAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationConnection** cmdlet removes a connection from azure_2 Automation.

## EXAMPLES

### Example 1: Remove a connection
```
PS C:\>Remove-AzureRmAutomationConnection -AutomationAccountName "Contoso17" -Name "ContosoConnection" -ResourceGroupName "ResourceGroup01"
```

This command removes a certificate named ContosoConnection in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the automation account for which this cmdlet removes a connection.

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

### -Name
Specifies the name of the connection that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet removes a connection.

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

[Get-AzureRmAutomationConnection](68f56d1c-23a9-4cb5-8fe8-c3a1e7c2ac1a)

[New-AzureRmAutomationConnection](7fed73b4-73cf-4642-8e10-167ea6158372)

