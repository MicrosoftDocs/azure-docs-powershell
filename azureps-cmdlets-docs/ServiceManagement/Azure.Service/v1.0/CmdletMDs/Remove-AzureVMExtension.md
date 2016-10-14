---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVMExtension.md
schema: 2.0.0
---

# Remove-AzureVMExtension

## SYNOPSIS
Removes resource extensions from a virtual machine.

## SYNTAX

### RemoveByExtensionName (Default)
```
Remove-AzureVMExtension [-ExtensionName] <String> [-Publisher] <String> -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### RemoveByReferenceName
```
Remove-AzureVMExtension [-ReferenceName] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RemoveAll
```
Remove-AzureVMExtension [-RemoveAll] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVMExtension** cmdlet removes resource extensions from a virtual machine.

## EXAMPLES

### Example 1: Remove an extension using a specific name and publisher
```
PS C:\>$VM = Remove-AzureVMExtension -VM $VM -ExtensionName $EXT -Publisher $PUB;
```

This command removes an extension with the specified name and publisher.

### Example 2: Remove all extensions from a specific virtual machine
```
PS C:\>$VM = Remove-AzureVMExtension -VM $VM -RemoveAll;
```

This command removes all extensions from the specified virtual machine as stored in the variable $VM.

## PARAMETERS

### -ExtensionName
Specifies the extension name that this cmdlet removes.

```yaml
Type: String
Parameter Sets: RemoveByExtensionName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the extension publisher.

```yaml
Type: String
Parameter Sets: RemoveByExtensionName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ReferenceName
Specifies the reference name of the extension.

```yaml
Type: String
Parameter Sets: RemoveByReferenceName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveAll
Indicates that this cmdlet removes all resource extensions from the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveAll
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

[Get-AzureVMExtension](.\Get-AzureVMExtension.md)

[Set-AzureVMExtension](.\Set-AzureVMExtension.md)

[Azure Service Cmdlets](.\Azure.Service.md)

