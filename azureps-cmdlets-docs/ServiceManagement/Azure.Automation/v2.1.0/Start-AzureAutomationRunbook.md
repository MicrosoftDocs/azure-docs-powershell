---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0A3F76C8-E2CE-4B62-B7D7-9C8FB43CE545
---

# Start-AzureAutomationRunbook

## SYNOPSIS
Starts a runbook job.

## SYNTAX

```
Start-AzureAutomationRunbook -Name <String> [-Parameters <IDictionary>] [-RunOn <String>]
 [-AutomationAccountName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureAutomationRunbook** cmdlet starts a Microsoft Azure Automation runbook job.
Specify the ID or name of a runbook.

## EXAMPLES

### Example 1: Start a runbook job
```
PS C:\> Start-AzureAutomationRunbook -AutomationAccountName "Contoso17" -Name "Runbk01"
```

This command starts a runbook job for the runbook named Runbk01 in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account.

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

### -Name
Specifies the name of a runbook.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RunbookName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parameters

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile

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

### -RunOn

```yaml
Type: String
Parameter Sets: (All)
Aliases: HybridWorker

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## NOTES

## RELATED LINKS

[Get-AzureAutomationRunbook](./Get-AzureAutomationRunbook.md)

[New-AzureAutomationRunbook](./New-AzureAutomationRunbook.md)

[Publish-AzureAutomationRunbook](./Publish-AzureAutomationRunbook.md)

[Remove-AzureAutomationRunbook](./Remove-AzureAutomationRunbook.md)

[Set-AzureAutomationRunbook](./Set-AzureAutomationRunbook.md)


