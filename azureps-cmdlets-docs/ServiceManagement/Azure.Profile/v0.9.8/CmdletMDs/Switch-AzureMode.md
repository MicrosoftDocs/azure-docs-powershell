---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=394398
schema: 2.0.0
---

# Switch-AzureMode

## SYNOPSIS
Switches between the Azure and Azure Resource Manager modules

## SYNTAX

```
Switch-AzureMode [-Name] <String> [-Global] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Switch-AzureMode** cmdlet switches between the Azure and Azure Resource Manager (AzureResourceManager) modules.
These modules are not designed to be used in the same session.
To determine which module is in your current session, use the Get-Module cmdlet.

NOTE: The **AzureResourceManager** module is currently in preview.
It might not provide the same management capabilities as the Azure module.

Beginning in version 0.8,0, the Azure PowerShell installation includes both Azure modules and Azure Profile, a module of commands common to both modules.
When you use the Azure PowerShell cmdlets, the Azure and Azure Profile modules are imported into the session by default.
To remove the Azure module from the session and import the Azure Resource Manager module, use **Switch-AzureMode**.
And, to switch back to the Azure module, just use **Switch-AzureMode** again.

The Azure module includes cmdlets that help you to manage your Azure account in the traditional way.
The cmdlets get, create, change, and remove individual resources such as storage accounts, virtual machines, SQL databases, web sites, media services, and cloud services.

The new Azure Resource Manager module, introduced in Azure PowerShell version 0.8.0, lets you manage your resources in an entirely new way.
Instead of creating individual resources and trying to use them together, begin by imagining the service you want to create, such as a web portal, a blog, a photo gallery, a commerce site, or a wiki.
Select a resource group template, including one of dozens in the Azure template gallery, or create your own.
Each template provides a model of a complex service, complete with the resources that you need to support the service.
Then use the template to create a resource group and its resources, and deploy and manage the related resources as a unit.

You can use **Switch-AzureMode** to switch between Azure modules as often as you like.
To set an Azure module as the default for all sessions, use the Global parameter when switching between modes.

## EXAMPLES

### Example 1: Switch to the Azure Resource Manager module
```
PS C:\>Switch-AzureMode -Name AzureResourceManager
PS C:\>Switch-AzureMode -Name AzureServiceManagement
```

This command shows you how to switch between modules.
The first command uses the **Switch-AzureMode** cmdlet to switch to the Azure Resource Manager module.
The second command uses the **Switch-AzureMode** cmdlet to switch back to the Azure module.

When you import either module, the AzureProfile module, which includes commands common to both modules, including Add-AzureAccount, Get-AzureSubscription, and Switch-AzureMode, is imported, too.

### Example 2: Switch all sessions to the Azure Resource Manager module
```
PS C:\>Switch-AzureMode -Name AzureResourceManager -Global
```

This command uses the Global parameter of Switch-AzureMode to switch all Windows Azure PowerShell sessions to the Azure Resource Manager module.
If you close this session and open an new one, the Azure Resource Manager module is imported by default.

The **Global** parameter requires administrator permissions.
To run this command, start Windows PowerShell with the "Run as administrator" option.

## PARAMETERS

### -Name
Switches to the specified module.
To switch to the Azure Resource Manager  module, type **AzureResourceManager**.
To switch to the Azure module, type **AzureServiceManagement**.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Global
Switches all Windows PowerShell session to the specified Azure module.
Use this parameter to save your module selection for other sessions.
This parameter is optional.
By default, the switch affects only the current session.

This parameter requires administrator permissions.
To use this parameter, start Windows PowerShell with the "Run as administrator" option.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
This parameter requires administrator permissions.
To use this parameter, start Windows PowerShell with the "Run as administrator" option.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES
* **Switch-AzureMode** is introduced in version 0.8.0 of the Azure modules. To get the version of your module, type: (Get-Module \<ModuleName\>).Version
* The **Switch-AzureMode** cmdlet is exported by the AzureProfile module. The AzureProfile module is compatible with both the Azure and AzureResourceManager modules and is imported automatically whenever either module is imported.

## RELATED LINKS

[Azure Resource Manager Cmdlets](http://go.microsoft.com/fwlink/?LinkID=394765)

[Azure Service Management Cmdlets](http://go.microsoft.com/fwlink/?LinkID=396348)

[Azure Profile Cmdlets](http://go.microsoft.com/fwlink/?LinkID=394766)

