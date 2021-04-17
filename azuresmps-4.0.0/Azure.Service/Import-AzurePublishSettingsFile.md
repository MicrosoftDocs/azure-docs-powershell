---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 79D64D7C-6671-4F03-8776-70A716F36512
online version:
schema: 2.0.0
---

# Import-AzurePublishSettingsFile

## SYNOPSIS
Imports a publish settings file that lets you manage your Azure accounts in Windows PowerShell.

## SYNTAX

```
Import-AzurePublishSettingsFile -PublishSettingsFile <String> [-Environment <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzurePublishSettingsFile** cmdlet imports a publish settings file (*.publishsettings) that contains information about your Azure accounts and saves a subscription data file on your computer.
When the cmdlet completes, you can manage your Azure accounts in Windows PowerShell.

Before running **Import-AzurePublishSettingsFile**, run **Get-AzurePublishSettingsFile**, which downloads and saves the publish settings file so you can import it.

To make your Azure account available to Windows PowerShell, you can use a publish settings file or the **Add-AzureAccount** cmdlet.
Publish settings files let you prepare the session in advance so you can run scripts and background jobs unattended.
However, not all services support publish settings files.
For example, the **AzureResourceManager** module does not support publish settings files.

**Security Note:** Publish settings files contain a management certificate that is encoded, but not encrypted.
If  malicious users access your publish settings file,  they might be able to edit, create, and delete your Azure services.
As a security best practice, save the file to a location in your Downloads or Documents folder and then delete it after using **Import-AzurePublishSettingsFile** cmdlet to import the settings.

## EXAMPLES

### Example 1: Import a file
```
PS C:\> Import-AzurePublishSettingsFile -PublishSettingsFile C:\Temp\MyAccount.publishsettings
```

This command imports the "C:\Temp\MyAccount.publishsettings" file.

## PARAMETERS

### -Environment
Specifies an Azure environment.

An Azure environment an independent deployment of Microsoft Azure, such as AzureCloud for global Azure and AzureChinaCloud for Azure operated by 21Vianet in China.
You can also create on-premises Azure environments by using Azure Pack and the WAPack cmdlets.
For more information, see [Azure Pack](/previous-versions/azure/windows-server-azure-pack/).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PublishSettingsFile
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You can pipe input to this cmdlet by property name, but not by value.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES
* A "publish settings file" is an XML file with a .publishsettings file name extension. The file contains an encoded certificate that provides management credentials for your Azure subscriptions. After you import this file, delete it to avoid security risks.
* A "subscription data file" is an XML file that can be saved on your computer safely. By default, it's saved in your roaming user profile ($home/AppData/Roaming).

## RELATED LINKS

[How to Install and Configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/install-configure-powershell/)

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)


