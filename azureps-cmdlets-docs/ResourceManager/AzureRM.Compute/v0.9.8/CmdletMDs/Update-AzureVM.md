---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Update-AzureVM

## SYNOPSIS
Updates the state of an Azure virtual machine.

## SYNTAX

### ResourceGroupNameParameterSetName (Default)
```
Update-AzureVM -VM <PSVirtualMachine> [-Tags <Hashtable[]>] -ResourceGroupName <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### IdParameterSetName
```
Update-AzureVM -VM <PSVirtualMachine> [-Tags <Hashtable[]>] -Id <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureVM** cmdlet updates the state of an Azure virtual machine to the state of a virtual machine object.

## EXAMPLES

### Example 1: Update a virtual machine
```
PS C:\>Update-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -VM $VirtualMachine
```

This command updates the virtual machine named VirtualMachine07 in ResourceGroup11.
The command updates it by using another virtual machine object, stored in the $VirtualMachine variable.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.

## PARAMETERS

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
Parameter Sets: ResourceGroupNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
@{Text=}```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies a local virtual machine object.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.
This virtual machine object contains the updated state for the virtual machine.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Id
The resource group name.```yaml
Type: String
Parameter Sets: IdParameterSetName
Aliases: 

Required: True
Position: Named
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

[Get-AzureVM](.\Get-AzureVM.md)

[New-AzureVM](.\New-AzureVM.md)

[Remove-AzureVM](.\Remove-AzureVM.md)

[Restart-AzureVM](.\Restart-AzureVM.md)

[Start-AzureVM](.\Start-AzureVM.md)

[Stop-AzureVM](.\Stop-AzureVM.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

