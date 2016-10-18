---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
ms.assetid: 90910030-C988-41DF-ADE1-C4FCFE4A1C7E
---

# Update-AzureVM

## SYNOPSIS
Modifies the configuration of an Azure virtual machine.

## SYNTAX

```
Update-AzureVM [-Name] <String> -VM <PersistentVM> [-ServiceName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureVM** cmdlet accepts update information for the specified virtual machine and initiates the update.
You can add or remove data disks, modify the cache mode of data or operating system disks, change the network endpoints, or change the size of the virtual machine.

## EXAMPLES

### Example 1: Update the size of a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "ContosoService03" -Name "VirtualMachine04" | Set-AzureVMSize -InstanceSize "Medium" | Update-AzureVM
```

This command changes the size of the virtual machine named VirtualMachine04, running in the service named ContosoService03, to Medium.

### Example 2: Add a data disk to a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "ContosoService03" -Name "VirtualMachine05" | Add-AzureDataDisk -CreateNew -MediaLocation "https://ContosoStore1.blob.core.azure.com/vhds/Disk22.vhd" -DiskSizeInGB 128 -DiskLabel "Data-128" -LUN 0 | Update-AzureVM
```

This command adds a new data disk to the virtual machine named VirtualMachine05, running in the service named ContosoService03.

## PARAMETERS

### -Name
Specifies the name of the virtual machine to update.

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
Specifies the virtual machine object that includes updated settings.

```yaml
Type: PersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the Azure service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\Get-AzureVM.md)

[New-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\New-AzureVM.md)

[New-AzureVMConfig](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\New-AzureVMConfig.md)

[Remove-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\Remove-AzureVM.md)

[Restart-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\Restart-AzureVM.md)

[Set-AzureVMSize](.\Set-AzureVMSize.md)

[Start-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\Start-AzureVM.md)

[Stop-AzureVM](..\..\..\..\ResourceManager\AzureRM.Compute\v0.9.8\CmdletMDs\Stop-AzureVM.md)


