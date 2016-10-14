---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMAccessExtension.md
schema: 2.0.0
---

# Set-AzureVMAccessExtension

## SYNOPSIS
Adds the VMAccess extension to a virtual machine.

## SYNTAX

```
Set-AzureVMAccessExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String>
 [[-TypeHandlerVersion] <String>] [[-UserName] <String>] [[-Password] <String>] [[-Location] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMAccessExtension** cmdlet adds the Virtual Machine Access (VMAccess) Virtual Machine Extension to a virtual machine.
VMAccess can reset the virtual machine user name and password.

## EXAMPLES

### Example 1: Add a VMAccess extension
```
PS C:\>   Set-AzureVMAccessExtension -ResourceGroupName "ResrouceGroup11" -Location "Central US" -VMName "VirtualMachine07" -Name "ContosoTest" -TypeHandlerVersion "2.0" -UserName "PFuller" -Password "Password"
```

This command adds a VMAccess extension for the virtual machine named VirtualMachine07 in ResrouceGroup11.
The command specifies the name and type handler version for VMAccess.

## PARAMETERS

### -Location
Specifies the location of the virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the extension that this cmdlet adds.```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies the new password of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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

### -UserName
Specifies the new user name for the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine. This cmdlet adds VMAccess for the virtual machine that this parameter specifies.```yaml
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

[Get-AzureVMAccessExtension](.\Get-AzureVMAccessExtension.md)

[Remove-AzureVMAccessExtension](.\Remove-AzureVMAccessExtension.md)

[Set-AzureVMExtension](.\Set-AzureVMExtension.md)

[Get-AzureVMExtensionImage](.\Get-AzureVMExtensionImage.md)

