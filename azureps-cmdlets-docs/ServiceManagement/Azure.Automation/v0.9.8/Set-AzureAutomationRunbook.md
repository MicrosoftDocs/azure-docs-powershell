---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=397915
schema: 2.0.0
ms.assetid: BE258F6F-5208-43EB-BD9E-B97B617B5C2A
---

# Set-AzureAutomationRunbook

## SYNOPSIS
Modifies the configuration of a runbook.

## SYNTAX

```
Set-AzureAutomationRunbook [-Name] <String> [-Description <String>] [-Tags <String[]>] [-LogProgress <Boolean>]
 [-LogVerbose <Boolean>] [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureAutomationRunbook** cmdlet modifies the configuration of a Microsoft Azure Automation runbook.

## EXAMPLES

### Example 1: Enable verbose logging for a runbook
```
PS C:\> Set-AzureAutomationRunbook -AutomationAccountName "Contoso17" -Name "MyRunbook" -LogVerbose $True
```

This command enables verbose logging for the jobs of the specified runbook in the Azure Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
@{Text=}

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

### -Description
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogProgress
@{Text=}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogVerbose
@{Text=}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: RunbookName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
@{Text=}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureProfile
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

### Microsoft.Azure.Commands.Automation.Model.Runbook

## NOTES

## RELATED LINKS

[Get-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Get-AzureAutomationRunbook.md)

[New-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\New-AzureAutomationRunbook.md)

[Publish-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Publish-AzureAutomationRunbook.md)

[Remove-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Remove-AzureAutomationRunbook.md)

[Start-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Start-AzureAutomationRunbook.md)


