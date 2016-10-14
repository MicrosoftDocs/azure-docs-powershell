---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Get-AzureSubnet

## SYNOPSIS
Gets a list of subnets associated with the specified Azure virtual machine.

## SYNTAX

```
Get-AzureSubnet -VM <IPersistentVM> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSubnet** cmdlet returns a list the subnets associated with the specified virtual machine.
Use **Get-AzureVM** to specify the virtual machine.

## EXAMPLES

### Example 1: Get subnets for a virtual machine
```
PS C:\>$VM = Get-AzureVM -ServiceName "ContosoService03" -Name "VirtualMachine01"
C:\PS> Get-AzureSubnet -VM $VM
```

The first command gets a virtual machine named VirtualMachine01 in the service named ContosoService03, and then stores it in the $VM variable.

The second command gets the Azure subnets for the virtual machine in $VM.

## PARAMETERS

### -VM
Specifies the virtual machine object from which to get the subnet list.

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

[Get-AzureVM](.\Get-AzureVM.md)

[Set-AzureSubnet](.\Set-AzureSubnet.md)

