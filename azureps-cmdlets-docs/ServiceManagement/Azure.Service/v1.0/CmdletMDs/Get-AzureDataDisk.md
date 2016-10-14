---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDataDisk.md
schema: 2.0.0
---

# Get-AzureDataDisk

## SYNOPSIS
Gets azure_2 data disks.

## SYNTAX

```
Get-AzureDataDisk [[-Lun] <Int32>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDataDisk** cmdlet gets an object that represents the data disks on an azure_2 virtual machine.
To get a specific data disk object, specify the logical unit number (LUN) of the disk.

## EXAMPLES

### Example 1: Get all data disks for a virtual machine
```
PS C:\>Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk
```

This command gets the virtual machine named VirtualMachine07 in the service named ContosoService by using the Get-AzureVM cmdlet.
The command passes the virtual machine to the current cmdlet by using the pipeline operator.
The current cmdlet gets all the data disks for this virtual machine.

### Example 2: Get a specific data disk for a virtual machine
```
PS C:\>Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk -LUN 2
```

This command gets the virtual machine named VirtualMachine07 in the service named ContosoService.
The command passes the virtual machine to the current cmdlet.
The current cmdlet gets the data disk that has the LUN 2.

## PARAMETERS

### -Lun
Specifies the LUN for the data drive in the virtual machine.
Valid values are: 0 through 15.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object for which this cmdlet gets data disks.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureDataDisk](.\Add-AzureDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureDataDisk](.\Remove-AzureDataDisk.md)

[Set-AzureDataDisk](.\Set-AzureDataDisk.md)

