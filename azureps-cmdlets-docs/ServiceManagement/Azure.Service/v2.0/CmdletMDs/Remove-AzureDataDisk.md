---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDataDisk.md
schema: 2.0.0
---

# Remove-AzureDataDisk

## SYNOPSIS
Removes a data disk from an Azure virtual machine.

## SYNTAX

```
Remove-AzureDataDisk [-LUN] <Int32> [-DeleteVHD] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDataDisk** cmdlet removes a data disk from an Azure virtual machine.
By default, this cmdlet does not remove the data disk blob from the storage account.

## EXAMPLES

### Example 1: Remove a data disk
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0
```

This command gets the virtual machine named VirtualMachine07 in the service named ContosoService by using the Get-AzureVM cmdlet.
The command passes the virtual machine to the current cmdlet by using the pipeline operator.
The current cmdlet removes the data disk that has the LUN 0.

### Example 2: Remove a data disk and the virtual hard disk file
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0 -DeleteVHD | Update-AzureVM
```

This command gets the virtual machine named VirtualMachine07 in the service named ContosoService.
The command passes the virtual machine to the current cmdlet.
The current cmdlet removes the data disk that has the LUN 0.
The command includes the *DeleteVHD* parameter.
Therefore, it also deletes the underlying virtual hard disk.
The command updates the virtual machine to reflect your changes by using the Update-AzureVM cmdlet.

## PARAMETERS

### -LUN
Specifies the logical unit number (LUN) for the data drive in the virtual machine.
Valid values are: 0 through 15.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteVHD
Indicates that this cmdlet removes the data disk and the virtual hard disk (VHD) from blob storage.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object that is attached to the data disk.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureDataDisk](.\Add-AzureDataDisk.md)

[Get-AzureDataDisk](.\Get-AzureDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Set-AzureDataDisk](.\Set-AzureDataDisk.md)

[Update-AzureVM](.\Update-AzureVM.md)

