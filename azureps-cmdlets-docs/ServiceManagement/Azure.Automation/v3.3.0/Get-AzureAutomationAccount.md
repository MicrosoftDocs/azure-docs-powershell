---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 7B2D9768-919B-4F54-BBC7-8882CC2C973A
online version: 
schema: 2.0.0
---

# Get-AzureAutomationAccount

## SYNOPSIS
Gets Azure Automation accounts.

## SYNTAX

```
Get-AzureAutomationAccount [[-Name] <String>] [[-Location] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationAccount** cmdlet gets the Microsoft Azure Automation accounts for your subscription.
An Automation account is a container for Automation resources that is isolated from the resources of other Automation accounts.
Automation resources include runbooks, jobs, and assets.

## EXAMPLES

### Example 1: Get an Automation account
```
PS C:\> Get-AzureAutomationAccount -Name "Contoso17"
```

This command gets the Automation account named Contoso17.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies an Azure location associated with Automation accounts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an Azure Automation account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## NOTES

## RELATED LINKS

[New-AzureAutomationAccount](./New-AzureAutomationAccount.md)

[Remove-AzureAutomationAccount](./Remove-AzureAutomationAccount.md)


