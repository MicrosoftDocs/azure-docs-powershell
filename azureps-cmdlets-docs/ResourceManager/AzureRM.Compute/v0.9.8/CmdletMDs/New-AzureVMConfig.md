---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Update-AzureVM.md
schema: 2.0.0
---

# New-AzureVMConfig

## SYNOPSIS
Creates a configurable virtual machine object.

## SYNTAX

```
New-AzureVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVMConfig** cmdlet creates a configurable local virtual machine object for Azure.
Configure a virtual machine object by using other cmdlets, such as **Set-AzureVMOperatingSystem**, **Set-AzureVMSourceImage**, **Add-AzureVMNetworkInterface**, and **Set-AzureVMOSDisk**.

## EXAMPLES

### Example 1: Create a virtual machine object
```
PS C:\>$AvailabilitySet = Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
```

The first command gets the availability set named AvailablitySet03 in the resource group named ResourceGroup11, and then stores that object in the $AvailabilitySet variable.

The second command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.
The virtual machine belongs to the availability set stored in $AvailabilitySet.

## PARAMETERS

### -AvailabilitySetId
Specifies the ID of an availability set. To obtain an availability set object, use the Get-AzureAvailabilitySet cmdlet. The availability set object contains an ID property.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -VMName
Specifies a name for the virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSize
Specifies the size for the virtual machine.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Update-AzureVM](.\Update-AzureVM.md)

[Set-AzureVMOperatingSystem](.\Set-AzureVMOperatingSystem.md)

[Set-AzureVMSourceImage](.\Set-AzureVMSourceImage.md)

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

