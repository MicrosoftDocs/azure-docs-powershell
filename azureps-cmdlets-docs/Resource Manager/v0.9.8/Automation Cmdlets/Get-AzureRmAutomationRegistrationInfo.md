---
external help file: RMAzure_Automation.xml
online version: c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43
schema: 2.0.0
---

# Get-AzureRmAutomationRegistrationInfo
## SYNOPSIS
Gets registration information for onboarding a DSC node or hybrid worker to Automation.

## SYNTAX

```
Get-AzureRmAutomationRegistrationInfo [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationRegistrationInfo** cmdlet gets the endpoint and keys required to onboard a Desired State Configuration (DSC) node or hybrid worker into an azure_2 Automation account.

## EXAMPLES

### Example 1: Get registration information
```
PS C:\>Get-AzureRmAutomationRegistrationInfo -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01"
```

This command gets the registration information for the Automation account named AutomationAccount01 in the Resource Group named ResourceGroup01.

## PARAMETERS

### -AutomationAccountName
Specifies the name of Automation account for which this cmdlet gets registration information.

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

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet gets registration information for the resource group that this parameter specifies.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationAccount](c9ec226d-3a4f-49d1-9b9f-df9d57bdfa43)

[Get-AzureRmAutomationDscNode](19472f94-5827-4878-a17a-d7bb10932861)

[New-AzureRmAutomationKey](3af84baf-d40e-43eb-a709-6f7caf657846)

