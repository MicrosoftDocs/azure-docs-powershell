---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 47D4FFAE-0756-447F-84A4-AE5247968D82
---

# Remove-AzureVMChefExtension

## SYNOPSIS
Removes the Chef extension applied on the virtual machine.

## SYNTAX

```
Remove-AzureVMChefExtension -VM <IPersistentVM> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVMChefExtension** cmdlet deletes the Chef extension applied on the virtual machine.

## EXAMPLES

### Example 1: Remove the Chef extension applied on the specified virtual machine
```
PS C:\> Remove-AzureVMChefExtension -VM $VM;
```

This command removes the Chef extension applied on the virtual machine.

## PARAMETERS

### -VM
Specifies the persistent virtual machine object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMChefExtension](./Get-AzureVMChefExtension.md)

[Set-AzureVMChefExtension](./Set-AzureVMChefExtension.md)


