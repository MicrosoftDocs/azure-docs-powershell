---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Remove-AzureVMNetworkInterface

## SYNOPSIS
Removes a network interface from a virtual machine.

## SYNTAX

```
Remove-AzureVMNetworkInterface [-VM] <PSVirtualMachine> -NetworkInterfaceIDs <String[]>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVMNetworkInterface** cmdlet removes a network interface from a virtual machine.

## EXAMPLES

### 1:
```

```

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

### -VM
Specifies the virtual machine from which this cmdlet removes a network interface.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.

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

### -NetworkInterfaceIDs
The virtual machine network interface's ID.```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Id, NicIds

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

