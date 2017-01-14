---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4A02E988-3415-4649-A969-4869E946C355
---

# New-WAPackVMSubnet

## SYNOPSIS
Creates a virtual machine subnet.

## SYNTAX

```
New-WAPackVMSubnet -VNet <VMNetwork> -Name <String> -Subnet <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-WAPackVMSubnet** cmdlet creates a virtual machine subnet.

## EXAMPLES

### Example 1: Create a virtual machine subnet
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> New-WAPackVMSubnet -VNet $VNet -Name "ContosoVMSubnet01" -Subnet "192.168.1.0/24"
```

The first command first retrieves the virtual machine network to which we want to add a new virtual machine subnet.
This virtual machine network is named ContosoVNet01.

The second command creates a virtual machine subnet using the previously retrieve virtual machine network, a name ContosoVMSubnet01 and a subnet 192.168.1.0/24.

## PARAMETERS

### -VNet
Specifies a VNet associated with the virtual machine subnet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a name for the virtual machine subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies a subnet for the virtual machine subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVMSubnet](./Get-WAPackVMSubnet.md)

[Get-WAPackVNet](./Get-WAPackVNet.md)

[Remove-WAPackVMSubnet](./Remove-WAPackVMSubnet.md)


