---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 91AB9561-D802-4340-A9B8-872BB2E835C4
---

# Get-AzureAutomationRegistrationInfo

## SYNOPSIS
Gets registration information for onboarding a DSC node or hybrid worker to Automation.

## SYNTAX

```
Get-AzureAutomationRegistrationInfo [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationRegistrationInfo** cmdlet gets the endpoint and keys required to onboard a PowerShell Desired State Configuration (DSC) node or hybrid worker into an Azure Automation account.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AutomationAccountName
Specifies the name of automation account for which this cmdlet gets registration information.

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
Specifies the name of a resource group.
This cmdlet gets registration information for the resource group that this parameter specifies.

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

[Get-AzureAutomationAccount](./Get-AzureAutomationAccount.md)

[Get-AzureAutomationDscNode](./Get-AzureAutomationDscNode.md)

[New-AzureAutomationKey](./New-AzureAutomationKey.md)


