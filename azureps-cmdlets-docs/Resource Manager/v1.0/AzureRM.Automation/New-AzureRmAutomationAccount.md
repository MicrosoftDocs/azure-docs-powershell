---
external help file: RMAzure_Automation.xml
online version: c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43
schema: 2.0.0
---

# New-AzureRmAutomationAccount
## SYNOPSIS
Creates an Automation account.

## SYNTAX

```
New-AzureRmAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Plan]
 [-Tags <IDictionary>]
```

## DESCRIPTION
The **New-AzureRmAutomationAccount** cmdlet creates an azure_2 Automation account in a resource group.

An Automation account is a container for Automation resources that is isolated from the resources of other Automation accounts.
Automation resources include runbooks, Desired State Configuration (DSC) configurations, jobs, and assets.

## EXAMPLES

### Example 1: Create an automation account
```
PS C:\> New-AzureRmAutomationAccount -Name "ContosoAutomationAccount" -Location "East US" -ResourceGroupName "ResourceGroup01"
```

This command creates a new automation account named ContosoAutomationAccount in the East US region.

## PARAMETERS

### -Location
Specifies the location in which this cmdlet creates the Automation account.
To obtain valid locations, use the Get-AzureRMLocation cmdlet.

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

### -Name
Specifies a name for the Automation account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Plan
Specifies the plan for the Automation account.
Valid values are: 

-- Basic 
-- Free

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Free, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group to which this cmdlet adds an Automation account.

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

### -Tags
Specifies tags for the Automation account.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationAccount](c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43)

[Remove-AzureRmAutomationAccount](2a126e99-39dd-4c00-b2a6-bf6495d64345)

[Set-AzureRmAutomationAccount](7e2254d6-c3c3-4ec5-8f7d-a3a2a6f24969)

