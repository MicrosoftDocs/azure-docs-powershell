---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureServiceExtension.md
schema: 2.0.0
---

# Get-AzureServiceAvailableExtension

## SYNOPSIS
Gets information about the available extensions for hosted services.

## SYNTAX

### ListLatestExtensions (Default)
```
Get-AzureServiceAvailableExtension [[-ExtensionName] <String>] [[-ProviderNamespace] <String>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ListSingleVersion
```
Get-AzureServiceAvailableExtension [-ExtensionName] <String> [-ProviderNamespace] <String> [-Version] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ListAllVersions
```
Get-AzureServiceAvailableExtension [-ExtensionName] <String> [-ProviderNamespace] <String> [-AllVersions]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureServiceAvailableExtension** cmdlet gets information for the latest available extensions for hosted services.

## EXAMPLES

### Example 1: Get available extensions
```
PS C:\>Get-AzureServiceAvailableExtension

          ProviderNameSpace          : Microsoft.Windows.Azure.Extensions
          ExtensionName              : RDP
          Version                    : 1.0
          Label                      : Microsoft Azure Remote Desktop Extension
          Description                : Microsoft Azure Remote Desktop Extension
          HostingResources           : WebOrWorkerRole
          ThumbprintAlgorithm        : sha1
          PublicConfigurationSchema  : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PublicConfig"><xs:complexType><xs:sequence><xs:element
          name="UserName" type="xs:string" minOccurs="1" /><xs:element name="Expiration" type="xs:string" minOccurs="1"
          /></xs:sequence></xs:complexType></xs:element></xs:schema>
          PrivateConfigurationSchema : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PrivateConfig"><xs:complexType><xs:sequence><xs:element
          name="Password" type="xs:string" /></xs:sequence></xs:complexType></xs:element></xs:schema>
          OperationDescription       : Get-AzureServiceAvailableExtension
          OperationId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
          OperationStatus            : Succeeded
```

This command gets all available extensions.

### Example 2: Get extensions in a specified namespace
```
PS C:\>Get-AzureServiceAvailableExtension -ProviderNamespace Microsoft.Windows.Azure.Extensions -ExtensionName "RDP" -AllVersions

          ProviderNameSpace          : Microsoft.Windows.Azure.Extensions
          ExtensionName              : RDP
          Version                    : 1.0.0.1
          Label                      : Microsoft Azure Remote Desktop Extension
          Description                : Microsoft Azure Remote Desktop Extension
          HostingResources           : WebOrWorkerRole
          ThumbprintAlgorithm        : sha1
          PublicConfigurationSchema  : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PublicConfig"><xs:complexType><xs:sequence><xs:element
          name="UserName" type="xs:string" minOccurs="1" /><xs:element name="Expiration" type="xs:string" minOccurs="1"
          /></xs:sequence></xs:complexType></xs:element></xs:schema>
          PrivateConfigurationSchema : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PrivateConfig"><xs:complexType><xs:sequence><xs:element
          name="Password" type="xs:string" /></xs:sequence></xs:complexType></xs:element></xs:schema>
          OperationDescription       : Get-AzureServiceAvailableExtension
          OperationId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
          OperationStatus            : Succeeded
```

This command gets the extensions with a specified name in a specified namespace.

### Example 3: Get a specific version of an extension
```
PS C:\>Get-AzureServiceAvailableExtension -ProviderNamespace Microsoft.Windows.Azure.Extensions -ExtensionName "RDP" -Version 1.0.0.1

          ProviderNameSpace          : Microsoft.Windows.Azure.Extensions
          ExtensionName              : RDP
          Version                    : 1.0.0.1
          Label                      : Microsoft Azure Remote Desktop Extension
          Description                : Microsoft Azure Remote Desktop Extension
          HostingResources           : WebOrWorkerRole
          ThumbprintAlgorithm        : sha1
          PublicConfigurationSchema  : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PublicConfig"><xs:complexType><xs:sequence><xs:element
          name="UserName" type="xs:string" minOccurs="1" /><xs:element name="Expiration" type="xs:string" minOccurs="1"
          /></xs:sequence></xs:complexType></xs:element></xs:schema>
          PrivateConfigurationSchema : <?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified"
          xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="PrivateConfig"><xs:complexType><xs:sequence><xs:element
          name="Password" type="xs:string" /></xs:sequence></xs:complexType></xs:element></xs:schema>
          OperationDescription       : Get-AzureServiceAvailableExtension
          OperationId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
          OperationStatus            : Succeeded
```

This command gets information about a specific version of an extension.

## PARAMETERS

### -ExtensionName
Specifies the extension name.

```yaml
Type: String
Parameter Sets: ListLatestExtensions
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ListSingleVersion, ListAllVersions
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderNamespace
Specifies the extension provider namespace.

```yaml
Type: String
Parameter Sets: ListLatestExtensions
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ListSingleVersion, ListAllVersions
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Version
Specifies the extension version.

```yaml
Type: String
Parameter Sets: ListSingleVersion
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllVersions
Indicates that this cmdlet gets all versions of an extension.

```yaml
Type: SwitchParameter
Parameter Sets: ListAllVersions
Aliases: 

Required: True
Position: 2
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

[Get-AzureServiceExtension](.\Get-AzureServiceExtension.md)

