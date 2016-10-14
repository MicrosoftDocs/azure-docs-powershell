---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Get-AzureAutomationModule.md
schema: 2.0.0
---

# New-AzureAutomationModule

## SYNOPSIS
Imports a module into Automation.

## SYNTAX

```
New-AzureAutomationModule [-Name] <String> [-ContentLink] <Uri> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureAutomationModule** cmdlet imports a module into Azure Automation.
This command accepts a compressed file that has a .zip file name extension.
The file contains a folder that includes a file that is one of the following types: 

- Azure PowerShell module, which has a .psm1 file name extension 
- Azure PowerShell module manifest, which has a .psd1 file name extension 
- Dynamic link library, which has a .dll file name extension

The name of the .zip file, the name of the folder, and the name of the file in the folder must be the same.

Specify the .zip file as a URL that this computer can access.

## EXAMPLES

### Example 1: Import a module
```
PS C:\> New-AzureAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLink "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip" -ResourceGroupName "ResourceGroup01"
```

This command imports a module named ContosoModule into the Azure Automation account named Contoso17.
The module is stored in an Azure blob in a storage account named contosostorage and a container named modules.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet imports a module.

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

### -ContentLink
Specifies the URL of the .zip file that contains a module that this cmdlet imports.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the module that this cmdlet imports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Specifies the name of a resource group for which this cmdlet imports a module.```yaml
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

[Get-AzureAutomationModule](.\Get-AzureAutomationModule.md)

[Remove-AzureAutomationModule](.\Remove-AzureAutomationModule.md)

[Set-AzureAutomationModule](.\Set-AzureAutomationModule.md)

