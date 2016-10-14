---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVMAccessExtension.md
schema: 2.0.0
---

# Set-AzureVMAccessExtension

## SYNOPSIS
Sets the VMAccess extension for a virtual machine.

## SYNTAX

### EnableAccessExtension (Default)
```
Set-AzureVMAccessExtension [[-UserName] <String>] [[-Password] <String>] [[-ReferenceName] <String>]
 [[-Version] <String>] [-ForceUpdate] -VM <IPersistentVM> [-Profile <AzureProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### DisableAccessExtension
```
Set-AzureVMAccessExtension [-Disable] [[-ReferenceName] <String>] [[-Version] <String>] [-ForceUpdate]
 -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### UninstallAccessExtension
```
Set-AzureVMAccessExtension [-Uninstall] [[-ReferenceName] <String>] [[-Version] <String>] [-ForceUpdate]
 -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMAccessExtension** cmdlet sets the VMAccess extension for the virtual machine.

## EXAMPLES

### Example 1: Set the VMAccess extension applied to a specified virtual machine
```
PS C:\>Set-AzureVMAccessExtension -VM $VM -UserName $User -Password $PWD;
```

This command sets the VMAccess extension applied to the specified virtual machine as stored in the variable $VM.

## PARAMETERS

### -UserName
Specifies the user name that this cmdlet uses to reset the virtual machine's credential.

```yaml
Type: String
Parameter Sets: EnableAccessExtension
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies the password for resetting the virtual machine's credential.

```yaml
Type: String
Parameter Sets: EnableAccessExtension
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferenceName
Specifies the reference name of the access extension.

This is a user-defined string that is used to refer to an extension.
It is specified when the extension is added to the virtual machine for the first time.
For subsequent updates, you should specify the previously used reference name while updating the extension.
The *ReferenceName* assigned to an extension is returned using the Get-AzureVM cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -Disable
Indicates that this cmdlet sets the Extension State to Disable.

```yaml
Type: SwitchParameter
Parameter Sets: DisableAccessExtension
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Uninstall
Indicates whether this cmdlet uninstalls the access extension.

```yaml
Type: SwitchParameter
Parameter Sets: UninstallAccessExtension
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceUpdate
Indicates that this cmdlet reapplies a configuration to an extension when the configuration has not been updated.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMAccessExtension](.\Get-AzureVMAccessExtension.md)

[Remove-AzureVMAccessExtension](.\Remove-AzureVMAccessExtension.md)

