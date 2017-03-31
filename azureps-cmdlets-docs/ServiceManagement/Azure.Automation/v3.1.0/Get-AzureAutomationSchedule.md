---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 436A6D6E-2280-475C-A1F5-6A6D72DAD9E7
online version: 
schema: 2.0.0
---

# Get-AzureAutomationSchedule

## SYNOPSIS
Gets an Azure Automation schedule.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationSchedule [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### ByName
```
Get-AzureAutomationSchedule [-Name] <String> [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationSchedule** cmdlet gets a Microsoft Azure Automation schedule.

## EXAMPLES

### Example 1: Get a schedule
```
PS C:\> Get-AzureAutomationSchedule -AutomationAccountName "Contoso17" -Name "DailySchedule08"
```

This command gets the schedule named DailySchedule08.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Azure Automation account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -Name
Specifies the name of a schedule.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ScheduleName

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

### Microsoft.Azure.Commands.Automation.Model.Schedule

## NOTES

## RELATED LINKS

[New-AzureAutomationSchedule](./New-AzureAutomationSchedule.md)

[Remove-AzureAutomationSchedule](./Remove-AzureAutomationSchedule.md)

[Set-AzureAutomationSchedule](./Set-AzureAutomationSchedule.md)


