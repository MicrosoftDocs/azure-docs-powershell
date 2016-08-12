---
external help file: RMAzure_Automation.xml
online version: cd411497-be17-46f7-8708-519f02312553
schema: 2.0.0
---

# Export-AzureRmAutomationDscConfiguration
## SYNOPSIS
Exports a DSC configuration from Automation to a local file.

## SYNTAX

```
Export-AzureRmAutomationDscConfiguration [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Force] [-OutputFolder <String>] [-Slot] -Name <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Export-AzureRmAutomationDscConfiguration** cmdlet exports an APS Desired State Configuration (DSC) configuration from azure_2 Automation to a local file.
The exported file has a .ps1 file name extension.

## EXAMPLES

### Example 1: Export the published version of a DSC configuration
```
PS C:\>Export-AzureRmAutomationDscConfiguration -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -Name "Configuration01" -Slot Published -OutputFolder "C:\Users\PattiFuller\Desktop"
```

This command exports the published version of a DSC configuration in Automation to the specified folder, which is the desktop.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC that this cmdlet exports.

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
Indicates that this cmdlet replaces an existing local file with a new file that has the same name.

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
Specifies the name of the DSC configuration that this cmdlet exports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ConfigurationName

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -OutputFolder
Specifies the output folder where this cmdlet exports the DSC configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet exports a DSC configuration.

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

### -Slot
Specifies which version of the DSC configuration that this cmdlet exports.
Valid values are: 

-- Draft
-- Published 

The default value is Published.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Published, Draft

Required: False
Position: Named
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

[Get-AzureRmAutomationDscConfiguration](cd411497-be17-46f7-8708-519f02312553)

[Import-AzureRmAutomationDscConfiguration](9e316628-0101-4da8-8a9f-843f8442e52d)

