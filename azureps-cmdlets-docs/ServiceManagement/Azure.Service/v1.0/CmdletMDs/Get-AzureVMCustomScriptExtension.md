---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Remove-AzureVMCustomScriptExtension.md
schema: 2.0.0
---

# Get-AzureVMCustomScriptExtension

## SYNOPSIS
Gets information from an azure_2 virtual machine custom script extension.

## SYNTAX

```
Get-AzureVMCustomScriptExtension -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMCustomScriptExtension** cmdlet gets information from an azure_2 virtual machine custom script extension.

## EXAMPLES

### Example 1: Get an Azure virtual machine script extension
```
PS C:\>Get-AzureVMCustomScriptExtension -VM $VM;
```

This command gets an azure_2 virtual machine script extension stored in the variable $VM.

## PARAMETERS

### -VM
Specifies the persistent virtual machine object.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

## NOTES

## RELATED LINKS

[Remove-AzureVMCustomScriptExtension](.\Remove-AzureVMCustomScriptExtension.md)

[Set-AzureVMCustomScriptExtension](.\Set-AzureVMCustomScriptExtension.md)

[Azure Service Cmdlets](.\Azure.Service.md)

