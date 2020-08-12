---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: ACBE32E5-AA8C-43CA-9FF4-4B59906C6B85
online version: 
schema: 2.0.0
---

# Get-AzureVMImageDiskConfigSet

## SYNOPSIS
Gets a disk configuration set object from the input image context.

## SYNTAX

```
Get-AzureVMImageDiskConfigSet [[-ImageContext] <OSImageContext>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMImageDiskConfigSet** cmdlet gets a disk configuration set object from the input image context.

## EXAMPLES

### Example 1: Get a disk configuration set object from a virtual machine
```
PS C:\> Get-AzureVMImage -ImageName $Img | Get-AzureVMImageDiskConfigSet
```

This command gets a disk configuration set object from a virtual machine.

## PARAMETERS

### -ImageContext
Specifies the virtual machine image context.

```yaml
Type: OSImageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
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
Specifies an information variable.

```yaml
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.ServiceManagement.Model.VirtualMachineImageDiskConfigSet

## NOTES

## RELATED LINKS

[New-AzureVMImageDiskConfigSet](./New-AzureVMImageDiskConfigSet.md)

[Get-AzureVMImage](./Get-AzureVMImage.md)


