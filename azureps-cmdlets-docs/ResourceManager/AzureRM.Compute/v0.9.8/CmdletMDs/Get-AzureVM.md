---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\New-AzureVM.md
schema: 2.0.0
---

# Get-AzureVM

## SYNOPSIS
Gets the properties of a virtual machine.

## SYNTAX

### ListAllVirtualMachinesParamSet (Default)
```
Get-AzureVM [-Profile <AzureProfile>] [<CommonParameters>]
```

### ListVirtualMachineInResourceGroupParamSet
```
Get-AzureVM [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### GetVirtualMachineInResourceGroupParamSet
```
Get-AzureVM [-ResourceGroupName] <String> [-Name] <String> [-Status] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ListNextLinkVirtualMachinesParamSet
```
Get-AzureVM [-NextLink] <Uri> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVM** cmdlet gets the model view and instance view of an Azure virtual machine.
The model view is the user specified properties of the virtual machine.
The instance view is the instance level status of the virtual machine.
To get only the instance view of a virtual machine, specify the *Status* parameter.

## EXAMPLES

### Example 1: Get model and instance view properties
```
PS C:\>Get-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
```

This command gets the model view and instance view properties of the virtual machine named VirtualMachine07.

### Example 2: Get instance view properties
```
PS C:\>Get-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -Status
```

This command gets properties of the virtual machine named VirtualMachine07.
This command specifies the *Status* parameter.
Therefore, the command gets only the instance view properties.

### Example 3: Get properties for all virtual machines in a resource group
```
PS C:\> Get-AzureVM -ResourceGroupName "ResourceGroup11"
```

This command gets properties for all the virtual machines in the resource group named ResourceGroup11.

### Example 4: Get all virtual machines in your subscription
```
PS C:\>Get-AzureVM
```

This command gets all the virtual machines in your subscription.

## PARAMETERS

### -Name
Specifies the name of the virtual machine to get.

```yaml
Type: String
Parameter Sets: GetVirtualMachineInResourceGroupParamSet
Aliases: ResourceName, VMName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextLink
Specifies the next link.```yaml
Type: Uri
Parameter Sets: ListNextLinkVirtualMachinesParamSet
Aliases: 

Required: True
Position: 2
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
Specifies the name of a resource group.```yaml
Type: String
Parameter Sets: ListVirtualMachineInResourceGroupParamSet, GetVirtualMachineInResourceGroupParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Indicates that this cmdlet gets only the instance view of the virtual machine.```yaml
Type: SwitchParameter
Parameter Sets: GetVirtualMachineInResourceGroupParamSet
Aliases: 

Required: False
Position: 3
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

[New-AzureVM](.\New-AzureVM.md)

[Remove-AzureVM](.\Remove-AzureVM.md)

[Restart-AzureVM](.\Restart-AzureVM.md)

[Start-AzureVM](.\Start-AzureVM.md)

[Stop-AzureVM](.\Stop-AzureVM.md)

[Update-AzureVM](.\Update-AzureVM.md)

