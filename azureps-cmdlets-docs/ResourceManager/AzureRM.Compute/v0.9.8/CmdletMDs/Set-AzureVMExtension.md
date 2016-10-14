---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMExtension.md
schema: 2.0.0
---

# Set-AzureVMExtension

## SYNOPSIS
Updates extension properties or adds an extension to a virtual machine.

## SYNTAX

### Settings (Default)
```
Set-AzureVMExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String> [-Publisher] <String>
 [-ExtensionType] <String> [-TypeHandlerVersion] <String> [[-Settings] <Hashtable>]
 [[-ProtectedSettings] <Hashtable>] [[-Location] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SettingString
```
Set-AzureVMExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String> [-Publisher] <String>
 [-ExtensionType] <String> [-TypeHandlerVersion] <String> [[-SettingString] <String>]
 [[-ProtectedSettingString] <String>] [[-Location] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMExtension** cmdlet updates properties for existing Virtual Machine Extensions or adds an extension to a virtual machine.

## EXAMPLES

### Example 1: Modify settings by using hash tables
```
PS C:\>$Settings = @{"fileUris" = "[]"; "commandToExecute" = ""};
PS C:\> $ProtectedSettings = @{"storageAccountName" = $stoname; "storageAccountKey" = $stokey};
PS C:\> Set-AzureVMExtension -ResourceGroupName "ResourceGroup11" -Location "West US" -VMName "VirtualMachine22" -Name "ContosoTest" -Publisher "Contoso.Compute" -Type "CustomScriptExtension" -TypeHandlerVersion "1.1" -Settings $Settings -ProtectedSettings $ProtectedSettings;
```

The first two commands use standard Windows PowerShell ‚Â® syntax to create hash tables, and then stores those hash tables in the $Settings and $ProtectedSettings variables.
For more information, type `Get-Help about_Hash_Tables`.
The second command includes two values previously created and stored in variables.

The final command modifies an extension of the virtual machine named VirtualMachine22 in ResourceGroup11 according to the contents of $Settings and $ProtectedSettings.
The command specifies other required information that includes the publisher and the extension type.

### Example 2: Modify settings by using strings
```
PS C:\>$SettingsString = '{"fileUris":[],"commandToExecute":""}';
PS C:\> $ProtectedSettingsString = '{"storageAccountName":"' + $stoname + '","storageAccountKey":"' + $stokey + '"}';
PS C:\> Set-AzureVMExtension -ResourceGroupName "ResourceGroup11" -Location "West US" -VMName "VirtualMachine22" -Name "CustomScriptExtension" -Publisher "Contoso.Compute" -Type "CustomScriptExtension" -TypeHandlerVersion "1.1" -SettingString $SettingsString -ProtectedSettingString $ProtectedSettingsString ;
```

The first two commands create strings that contain settings, and then stores them in the $SettingsString and $ProtectedSettingsString variables.

The final command modifies an extension of the virtual machine named VirtualMachine22 in ResourceGroup11 according to the contents of $SettingsString and $ProtectedSettingsString.
The command specifies other required information that includes the publisher and the extension type.

## PARAMETERS

### -ExtensionType
Specifies the extension type.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an extension.```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

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

### -ProtectedSettings
Specifies private configuration for the extension, as a hash table. This cmdlet encrypts the private configuration.```yaml
Type: Hashtable
Parameter Sets: Settings
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtectedSettingString
Specifies private configuration for the extension, as a string. This cmdlet encrypts the private configuration.```yaml
Type: String
Parameter Sets: SettingString
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the name of the extension publisher.
The publisher provides a name when the publisher registers an extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Settings
Specifies public configuration for the extension, as a hash table. This cmdlet does not encrypt public configuration.```yaml
Type: Hashtable
Parameter Sets: Settings
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SettingString
Specifies public configuration for the extension, as a string. This cmdlet does not encrypt public configuration.```yaml
Type: String
Parameter Sets: SettingString
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Specifies the version of the extension to use for this virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine. This cmdlet modifies extensions for the virtual machine that this parameter specifies.```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

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

[Get-AzureVMExtension](.\Get-AzureVMExtension.md)

[Remove-AzureVMExtension](.\Remove-AzureVMExtension.md)

