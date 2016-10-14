---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Stop-WAPackVM

## SYNOPSIS
Stops a virtual machine.

## SYNTAX

```
Stop-WAPackVM [-Shutdown] [-VM] <VirtualMachine> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
ps_redir_wap This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The **Stop-WAPackVM** cmdlet stops a virtual machine.

## EXAMPLES

### Example 1: Stop a virtual machine
```
PS C:\>$VirtualMachine = Get-WAPackVM -Name "ContosoV126"PS C:\> Stop-WAPackVM -VM $VirtualMachine
```

The first command gets the virtual machine named ContosoV126 by using the **Get-WAPackVM** cmdlet, and then stores that object in the $VirtualMachine variable.

The second command stops the virtual machine stored in $VirtualMachine.

## PARAMETERS

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

### -Shutdown
Indicates that the cmdlet shuts down the operating system of the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine.
To obtain a virtual machine, use the **Get-WAPackVM** cmdlet.

```yaml
Type: VirtualMachine
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
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

[Get-WAPackVM](.\Get-WAPackVM.md)

[New-WAPackVM](.\New-WAPackVM.md)

[Remove-WAPackVM](.\Remove-WAPackVM.md)

[Restart-WAPackVM](.\Restart-WAPackVM.md)

[Resume-WAPackVM](.\Resume-WAPackVM.md)

[Set-WAPackVM](.\Set-WAPackVM.md)

[Start-WAPackVM](.\Start-WAPackVM.md)

[Suspend-WAPackVM](.\Suspend-WAPackVM.md)

