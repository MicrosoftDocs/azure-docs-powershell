---
external help file: SMAzure_Compute.xml
online version: 4b060a7d-da50-45ff-adb6-bcba63faa90b
schema: 2.0.0
---

# Remove-WAPackVM
## SYNOPSIS
Removes virtual machine objects.

## SYNTAX

```
Remove-WAPackVM [-VM] <VirtualMachine> [-PassThru] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  Azure WAPack Cmdletshttp://msdn.microsoft.com/library/dn776450.aspx.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The Remove-WAPackVM cmdlet removes virtual machine objects.

## EXAMPLES

### Example 1: Remove a virtual machine
```
PS C:\>$VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Remove-WAPackVM -VM $VirtualMachine
```

The first command gets the virtual machine named ContosoV126 by using the Get-WAPackVM cmdlet, and then stores that object in the $VirtualMachine variable.

The second command removes the virtual machine stored in $VirtualMachine.
The command prompts you for confirmation.

### Example 2: Remove a virtual machine without confirmation
```
PS C:\>$VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Remove-WAPackVM -VM $VirtualMachine -Force
```

The first command gets the virtual machine named ContosoV126 by using the Get-WAPackVM cmdlet, and then stores that object in the $VirtualMachine variable.

The second command removes the virtual machine stored in $VirtualMachine.
This command includes the Force parameter.
The command does not prompt you for confirmation.

## PARAMETERS

### -Force
Indicates that the cmdlet removes a virtual machine without prompting you for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet returns a Boolean value.
If the operation succeeds, the cmdlet returns a value of $True.
Otherwise, it returns a value of $False.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine.
To obtain a virtual machine, use the Get-WAPackVM cmdlet.

```yaml
Type: VirtualMachine
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVM](4b060a7d-da50-45ff-adb6-bcba63faa90b)

[New-WAPackVM](1f74deb4-e9b0-4aeb-8e13-b1554a4ebbec)

[Restart-WAPackVM](fd89742d-0d21-41e9-b3b1-5d8c638f8c6d)

[Resume-WAPackVM](d2594d2a-c0c6-4bca-8c81-9ed03b24d100)

[Set-WAPackVM](8b07e4cb-c677-4e6b-b034-25847da03dbf)

[Start-WAPackVM](8cc5bf6b-bf5b-427f-922d-57e4a99b2d55)

[Stop-WAPackVM](7f3e6c33-2196-4e24-95fd-e5763c6f7402)

[Suspend-WAPackVM](d8041113-5a71-447d-9bbe-dc6405aa6029)

