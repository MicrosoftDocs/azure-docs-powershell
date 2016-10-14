---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureVMImage.md
schema: 2.0.0
---

# Set-AzureOSDisk

## SYNOPSIS
Modifies the host cache mode of an azure_2 virtual machine.

## SYNTAX

### NoResize
```
Set-AzureOSDisk [-HostCaching] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Resize
```
Set-AzureOSDisk [[-HostCaching] <String>] [-ResizedSizeInGB] <Int32> -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureOSDisk** cmdlet modifies the host cache mode of the operating system disk of an azure_2 virtual machine.
The supported host cache modes are ReadOnly and ReadWrite.
If you run this cmdlet on a virtual machine that is running, that virtual machine restarts.

## EXAMPLES

### Example 1: Set the host cache mode to ReadOnly by using the pipeline
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine02" | Set-AzureOSDisk -HostCaching "ReadOnly"
```

This command gets the virtual machine named VirtualMachine02 in the service named ContosoService by using the **Get-AzureVM** cmdlet.
The command passes the virtual machine to the current cmdlet by using the pipeline operator.
The current cmdlet sets the host cache mode of the operating system disk of that virtual machine to be ReadOnly.

### Example 2: Set the host cache mode to ReadWrite
```
PS C:\>$VM = Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine02"
PS C:\> Set-AzureOSDisk "ReadWrite" -VM $myVM2
```

The first command gets the virtual machine named VirtualMachine02 in the service named ContosoService, and then stores it in the variable.

The second command sets the host cache mode of the operating system disk of that virtual machine to be ReadWrite.

## PARAMETERS

### -HostCaching
Specifies the host cache attribute for the operating system disk.
Valid values are: 

- ReadOnly 
- ReadWrite

```yaml
Type: String
Parameter Sets: NoResize
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Resize
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which this cmdlet modifies the operating system disk.
To obtain a virtual machine object, use the Get-AzureVM cmdlet.

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
ps_azureprofile_description

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResizedSizeInGB
Specifies a new size, in gigabytes, for the operating system disk.
The size must be larger than the current size.

```yaml
Type: Int32
Parameter Sets: Resize
Aliases: 

Required: True
Position: 1
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

[Add-AzureVMImage](.\Add-AzureVMImage.md)

[Get-AzureOSDisk](.\Get-AzureOSDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[Set-AzureDataDisk](.\Set-AzureDataDisk.md)

[Update-AzureVM](.\Update-AzureVM.md)

