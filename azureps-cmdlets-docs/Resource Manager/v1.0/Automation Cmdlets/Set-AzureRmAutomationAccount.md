---
external help file: RMAzure_Automation.xml
online version: c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43
schema: 2.0.0
---

# Set-AzureRmAutomationAccount
## SYNOPSIS
Modifies an Automation account.

## SYNTAX

```
Set-AzureRmAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Plan] [-Tags <IDictionary>]
```

## DESCRIPTION
The **Set-AzureRmAutomationAccount** cmdlet modifies an azure_2 Automation account.

For more information about Automation accounts, see the New-AzureRmAutomationAccount cmdlet.

## EXAMPLES

### Example 1: Set the tags for an Automation account
```
PS C:\>$Tags = @{"tag01"="value01";"tag02"="value02"}
PS C:\> Set-AzureRmAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Tags $Tags
```

The first command assigns two key/value pairs to the $Tags variable.

The second command sets tags in $Tags for the Automation account named AutomationAccount01.

### Example 2: Change the plan for an Automation account
```
PS C:\>Set-AzureRmAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Plan Basic
```

This command changes the plan to Basic for the Automation account named AutomationAccount01.

## PARAMETERS

### -Name
Specifies the name of the Automation account that this cmdlet modifies.

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
Specifies the name of a resource group that contains the Automation account that this cmdlet modifies.

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
Specifies Automation account tags for the Automation account.

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

[New-AzureRmAutomationAccount](1a996e7a-1de8-4533-a39a-c17cf1ab18fd)

[Remove-AzureRmAutomationAccount](2a126e99-39dd-4c00-b2a6-bf6495d64345)

