---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9FE50C57-F9E3-47C3-BAFE-DA75CEAEEAA0
---

# Remove-WAPackVMSubnet

## SYNOPSIS
Removes virtual machine subnet objects.

## SYNTAX

```
Remove-WAPackVMSubnet [-VMSubnet] <VMSubnet> [-PassThru] [-Force] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  [Azure WAPack Cmdlets](http://msdn.microsoft.com/library/dn776450.aspx) (http://msdn.microsoft.com/library/dn776450.aspx).
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Remove-WAPackVMSubnet** cmdlet removes virtual machine subnet objects.

## EXAMPLES

### Example 1: Remove a virtual machine subnet
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet01"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet
```

The first command gets the virtual machine subnet named ContosoVMSubnet01 by using the **Get-WAPackVMSubnet** cmdlet, and then stores that object in the $VMSubnet variable.
The second command removes the virtual machine subnet stored in $VMSubnet.
The command prompts you for confirmation.

### Example 2: Remove a virtual machine without confirmation
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet02"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet -Force
```

The first command gets the cloud service named ContosoVMSubnet02 by using the **Get-WAPackVMSubnet** cmdlet, and then stores that object in the $VMSubnet variable.
The second command removes the virtual machine subnet stored in $VMSubnet.
This command includes the *Force* parameter.
The command does not prompt you for confirmation.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnet
Specifies a virtual machine subnet.
To obtain a virtual machine subnet, use the **Get-WAPackVMSubnet** cmdlet.

```yaml
Type: VMSubnet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[New-WAPackVMSubnet](./New-WAPackVMSubnet.md)


