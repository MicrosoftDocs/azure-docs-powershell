---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397622
schema: 2.0.0
---

# Get-AzurePublishSettingsFile

## SYNOPSIS
Downloads the publish settings file for an Azure subscription.

## SYNTAX

```
Get-AzurePublishSettingsFile [[-Environment] <String>] [[-Realm] <String>] [-PassThru]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzurePublishSettingsFile** cmdlet downloads a publish settings file for a subscription in your account.
When the command completes, you can use the **Import-PublishSettingsFile** cmdlet to make the settings in the file available to Windows PowerShell.

To make your Azure account available to Windows PowerShell, you can use a publish settings file or the **Add-AzureAccount** cmdlet.
Publish settings files let you prepare the session in advance so you can run scripts and background jobs unattended.
However, not all services support publish settings files.
For example, the AzureResourceManager module does not support publish settings files.

When you run **Get-AzurePublishSettingsFile**, it opens your default browser and prompts you to sign into your Azure account, select a subscription, and select a file system location for the publish settings file.
Then, it downloads the publish settings file for your subscription into the file that you selected.

A "publish settings file" is an XML file with a .publishsettings file name extension.
The file contains an encoded certificate that provides management credentials for your Azure subscriptions.

**Security Note:** Publish settings files contains credentials that are used to administer your Azure subscriptions and services.
If  malicious users access your publish settings file,  they can edit, create, and delete your Azure services.
As a security best practice, save the file to a location in your Downloads or Documents folder and then delete it after using **Import-AzurePublishSettingsFile** cmdlet to import the settings.

This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

## EXAMPLES

### Example 1: Download a publish settings file
```
PS C:\>Get-AzurePublishSettingsFile
```

This command opens your default browser, connects to your Windows Azure account, and then downloads the .publishsettings file for your account.

### Example 2: Specify a realm
```
PS C:\>Get-AzurePublishSettingsFile -Realm contoso.com -Passthru
```

This command downloads the publish settings file for an account in the contoso.com domain.
Use a command with the **Realm** parameter when you sign into Azure with an organizational account, instead of a Microsoft account.

## PARAMETERS

### -Environment
Specifies an Azure environment.

An Azure environment an independent deployment of Microsoft Azure, such as AzureCloud for global Azure and AzureChinaCloud for Azure operated by 21Vianet in China.
You can also create on-premises Azure environments by using Azure Pack and the WAPack cmdlets.
For more information, see Azure Packhttp://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx (http://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Realm
Specifies the organization in an organizational ID.
For example, if you sign into Azure as admin@contoso.com, the value of the **Realm** parameter is contoso.com.
Use this parameter when you use an organizational ID to sign into the Azure portal.
This parameter is not required when you use a Microsoft account, such as an outlook.com or live.com account.

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

### -PassThru
Returns True ($true) if the command succeeds and False ($false) if it fails.
By default, this cmdlet does not return any output.
The **PassThru** parameter is typically used in conditional statements in functions and scripts.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
An Azure environment an independent deployment of Microsoft Azure, such as AzureCloud for global Azure and AzureChinaCloud for Azure operated by 21Vianet in China.
You can also create on-premises Azure environments by using Azure Pack and the WAPack cmdlets.
For more information, see Azure Packhttp://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx (http://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx).

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
You can pipe input to this cmdlet by property name, but not by value.

## OUTPUTS

### None or System.Boolean
When you use the **PassThru** parameter, this cmdlet returns a Boolean value.
Otherwise, this cmdlet does not return any output

## NOTES

## RELATED LINKS

[Add-AzureAccount](.\Add-AzureAccount.md)

[Import-AzurePublishSettingsFile](.\Import-AzurePublishSettingsFile.md)

