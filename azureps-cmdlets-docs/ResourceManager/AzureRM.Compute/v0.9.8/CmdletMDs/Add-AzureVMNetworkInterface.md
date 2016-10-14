---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\New-AzureVMConfig.md
schema: 2.0.0
---

# Add-AzureVMNetworkInterface

## SYNOPSIS
Adds a network interface to a virtual machine.

## SYNTAX

### GetNicFromNicId (Default)
```
Add-AzureVMNetworkInterface [-VM] <PSVirtualMachine> [-Id] <String> [-Primary] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### GetNicFromNicObject
```
Add-AzureVMNetworkInterface [-VM] <PSVirtualMachine>
 -NetworkInterface <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkInterface]>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureVMNetworkInterface** cmdlet adds a network interface to a virtual machine.
You can add an interface when you create a virtual machine or add one to an existing virtual machine.

## EXAMPLES

### Example 1: Add a network interface to a new virtual machine
```
PS C:\>$VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" 
PS C:\> Add-AzureVMNetworkInterface -VM $VirtualMachine -Id "/subscriptions/46fc8ea4-2de6-4179-8ab1-365da4121af4/resourceGroups/contoso/providers/Microsoft.Network/networkInterfaces/sshNIC"
```

The first command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.

The second command adds a network interface to the virtual machine stored in $VirtualMachine.

### Example 2: Add a network interface to an existing virtual machine
```
PS C:\>$VirtualMachine = Get-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> Add-AzureVMNetworkInterface -VM $VirtualMachine -Id "/subscriptions/46fc8ea4-2de6-4179-8ab1-365da4121af4/resourceGroups/contoso/providers/Microsoft.Network/networkInterfaces/sshNIC"
PS C:\> Update-AzureVM -ResourceGroupName "ResourceGroup11" -Name " VirtualMachine07" -VM $VirtualMachine
```

The first command gets the virtual machine named VirtualMachine07 by using the **Get-AzureVM** cmldet.
The command stores the virtual machine in the $VirtualMachine variable.

The second command adds a network interface to the virtual machine stored in $VirtualMachine.

The final command updates the state of the virtual machine stored in $VirtualMachine in ResourceGroup11.

## PARAMETERS

### -Id
Specifies the ID of a network interface to add to a virtual machine.
To obtain a network interface, use the **Get-AzureNetworkInterface** cmdlet.

```yaml
Type: String
Parameter Sets: GetNicFromNicId
Aliases: NicId, NetworkInterfaceId

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Primary
Indicates that this cmdlet adds the network interface as the primary interface.

```yaml
Type: SwitchParameter
Parameter Sets: GetNicFromNicId
Aliases: 

Required: False
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

### -VM
Specifies a local virtual machine object to which to add a network interface.
To create a virtual machine, use the **New-AzureVMConfig** cmdlet.
To obtain an existing virtual machine, use the **Get-AzureVM** cmdlet.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NetworkInterface
{{Fill NetworkInterface Description}}

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkInterface]
Parameter Sets: GetNicFromNicObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureVMConfig](.\New-AzureVMConfig.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

