---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVMDscExtension.md
schema: 2.0.0
---

# Get-AzureVMDscExtensionStatus

## SYNOPSIS
Gets the DSC extension status for all the virtual machines deployed in a cloud service or for a particular virtual machine in the service.

## SYNTAX

### GetStatusByServiceAndVMName (Default)
```
Get-AzureVMDscExtensionStatus [-ServiceName] <String> [[-Name] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### GetStatusByVM
```
Get-AzureVMDscExtensionStatus [-VM] <IPersistentVM> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMDscExtensionStatus** cmdlet gets the Desired State Configuration (DSC) extension status for all the virtual machines deployed in a cloud service or for a particular virtual machine in the service.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the virtual machine.

```yaml
Type: String
Parameter Sets: GetStatusByServiceAndVMName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service.

```yaml
Type: String
Parameter Sets: GetStatusByServiceAndVMName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object.

```yaml
Type: IPersistentVM
Parameter Sets: GetStatusByVM
Aliases: InputObject

Required: True
Position: 3
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

### Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.VirtualMachineDscExtensionStatusContext

## NOTES

## RELATED LINKS

[Get-AzureVMDscExtension](.\Get-AzureVMDscExtension.md)

[Remove-AzureVMDscExtension](.\Remove-AzureVMDscExtension.md)

[Set-AzureVMDscExtension](.\Set-AzureVMDscExtension.md)

