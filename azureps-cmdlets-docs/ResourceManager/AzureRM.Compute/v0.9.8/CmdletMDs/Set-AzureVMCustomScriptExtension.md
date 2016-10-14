---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMCustomScriptExtension.md
schema: 2.0.0
---

# Set-AzureVMCustomScriptExtension

## SYNOPSIS
Adds a custom script extension to a virtual machine.

## SYNTAX

### SetCustomScriptExtensionByContainerAndFileNames (Default)
```
Set-AzureVMCustomScriptExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String>
 [[-TypeHandlerVersion] <String>] [-ContainerName] <String> [-FileName] <String[]>
 [[-StorageAccountName] <String>] [[-StorageEndpointSuffix] <String>] [[-StorageAccountKey] <String>]
 [[-Run] <String>] [[-Argument] <String>] [[-Location] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetCustomScriptExtensionByUriLinks
```
Set-AzureVMCustomScriptExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String>
 [[-TypeHandlerVersion] <String>] [[-FileUri] <String[]>] [-Run] <String> [[-Argument] <String>]
 [[-Location] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMCustomScriptExtension** cmdlet adds a custom script Virtual Machine Extension to a virtual machine.
This extension allows you to run your own scripts on the virtual machine.

## EXAMPLES

### Example 1: Add a custom script
```
PS C:\>Set-AzureVMCustomScriptExtension -ResourceGroupName "ResourceGroup11" -Location "Central US" -VMName "VirtualMachine07" -Name "contosotest" -TypeHandlerVersion "1.1" -StorageAccountName "contoso" -StorageAccountKey <StorageKey> -FileName "contososcript.exe" -ContainerName "scripts"
```

This command adds a custom script to the virtual machine named VirtualMachine07.
The script file is contososcript.exe.

## PARAMETERS

### -Argument
Specifies arguments that the script extension passes to the script.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerName
Specifies the name of the Azure Storage container where this cmdlet stores the script.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileName
Specifies the name of the script file.

```yaml
Type: String[]
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileUri
Specifies the URI of the script file.

```yaml
Type: String[]
Parameter Sets: SetCustomScriptExtensionByUriLinks
Aliases: 

Required: False
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
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the custom script extension.```yaml
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

### -ResourceGroupName
Specifies the name of the resource group of the virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Run
Specifies the command to use that runs your script.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: RunFile, Command

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByUriLinks
Aliases: RunFile, Command

Required: True
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountKey
Specifies the key for the Azure Storage container.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the Azure Storage account where this cmdlet stores the script.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEndpointSuffix
Specifies the storage endpoint suffix.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Specifies the version of the extension to use for this virtual machine. To obtain the version, run the Get-AzureVMExtensionImage cmdlet with a value of Microsoft.Compute for the PublisherName parameter and VMAccessAgent for the Type parameter.```yaml
Type: String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine. This cmdlet adds the custom script extension for the virtual machine that this parameter specifies.```yaml
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

[Get-AzureVMCustomScriptExtension](.\Get-AzureVMCustomScriptExtension.md)

[Remove-AzureVMCustomScriptExtension](.\Remove-AzureVMCustomScriptExtension.md)

