---
external help file: RMAzure_Automation.xml
online version: 68762a05-73e2-4987-aac6-1021282cdad7
schema: 2.0.0
---

# New-AzureRmAutomationModule
## SYNOPSIS
Imports a module into Automation.

## SYNTAX

```
New-AzureRmAutomationModule [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-ContentLink] <Uri>
```

## DESCRIPTION
The **New-AzureRmAutomationModule** cmdlet imports a module into azure_2 Automation.
This command accepts a compressed file that has a .zip file name extension.
The file contains a folder that includes a file that is one of the following types: 

-- wps_2 module, which has a .psm1 or .dll file name extension 
-- wps_2 module manifest, which has a .psd1 file name extension

The name of the .zip file, the name of the folder, and the name of the file in the folder must be the same.

Specify the .zip file as a URL that the Automation service can access.

If you import a wps_2 module into Automation by using this cmdlet or the Set-AzureRmAutomationModule cmdlet, the operation is asynchronous.
The command finishes whether the import succeeds or fails.
To check whether it succeeded, run the following command:

\[CODE_Snippit\]PS C:\\\> $ModuleInstance = Get-AzureRmAutomationModule -Name \[CODE_Snippit\]ModuleName

Check the **ProvisioningState** property for a value of Succeeded.

## EXAMPLES

### Example 1: Import a module
```
PS C:\>New-AzureRmAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLink "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip" -ResourceGroupName "ResourceGroup01"
```

This command imports a module named ContosoModule into the Automation account named Contoso17.
The module is stored in an azure_2 blob in a storage account named contosostorage and a container named modules.

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
Accept pipeline input: True(ByPropertyName)
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
Accept pipeline input: True(ByPropertyName)
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
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet imports a module.

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

[Get-AzureRmAutomationModule](68762a05-73e2-4987-aac6-1021282cdad7)

[Remove-AzureRmAutomationModule](762b2b43-579b-4869-98f9-882aaf224686)

[Set-AzureRmAutomationModule](e47306c4-b17e-4651-8248-eb81ad448a17)

