---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Set-AzureVMSize

## SYNOPSIS
Sets the size of an Azure virtual machine.

## SYNTAX

```
Set-AzureVMSize [-InstanceSize] <String> -VM <IPersistentVM> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMSize** cmdlet updates the size of a virtual machine.
It has two parameters: *InstanceSize*, which is the new size of the virtual machine, and *VM*, which is a virtual machine object retrieved by using the Get-AzureVM cmdlet.
The result of **Set-AzureVMSize** can be piped to the Update-AzureVM cmdlet or stored in a variable for later use.
No actual change is made until **Update-AzureVM** is executed.

Note: This cmdlet will require the virtual machine to be re-provisioned and it might get a new IP address.

## EXAMPLES

### Example 1: Set the size of a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "MySvc1" -Name "MyVM3" | Set-AzureVMSize "Small" | Update-AzureVM
```

This command updates a virtual machine to size "Small".

## PARAMETERS

### -InstanceSize
Specifies the size of the machine.

The acceptable values for this parameter are:

--ExtraSmall
--Small
--Medium
--Large
--ExtraLarge
--A5
--A6
--A7

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object that this cmdlet sets the size of.

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

[Update-AzureVM](.\Update-AzureVM.md)

