---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Get-AzureVMSize

## SYNOPSIS
Gets available virtual machine sizes.

## SYNTAX

### ListVirtualMachineSizeParamSet (Default)
```
Get-AzureVMSize [-Location] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ListAvailableSizesForAvailabilitySet
```
Get-AzureVMSize [-ResourceGroupName] <String> [-AvailabilitySetName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ListAvailableSizesForVirtualMachine
```
Get-AzureVMSize [-ResourceGroupName] <String> [-VMName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMSize** cmdlet gets available virtual machine sizes.

## EXAMPLES

### Example 1: Get sizes for a location
```
PS C:\>Get-AzureVMSize -Location "Central US"
```

This command gets the available sizes for virtual machines in the specified location.

### Example 2: Get sizes for an availability set
```
PS C:\>Get-AzureVMSize -ResourceGroupName "ResourceGroup03" -AvailabilitySetName "AvailabilitySet17"
```

This command gets available sizes for virtual machines that you can deploy in the availability set named AvailabilitySet17.

### Example 3: Get sizes for an existing virtual machine
```
PS C:\>Get-AzureVMSize -ResourceGroupName "ResourceGroup03" -VMName "VirtualMachine12"
```

This command gets available sizes for the existing virtual machine named VirtualMachine12.
You can resize this virtual machine to the sizes that this command gets.

## PARAMETERS

### -AvailabilitySetName
Specifies the name of the Availability Set for which this cmdlet gets the available virtual machine sizes.

```yaml
Type: String
Parameter Sets: ListAvailableSizesForAvailabilitySet
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location for which this cmdlet gets the available virtual machine sizes.

```yaml
Type: String
Parameter Sets: ListVirtualMachineSizeParamSet
Aliases: 

Required: True
Position: 1
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

### -ResourceGroupName
Specifies the name of the resource group of the virtual machine.

```yaml
Type: String
Parameter Sets: ListAvailableSizesForAvailabilitySet, ListAvailableSizesForVirtualMachine
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine that this cmdlet gets the available virtual machine sizes for resizing.

```yaml
Type: String
Parameter Sets: ListAvailableSizesForVirtualMachine
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

[Get-AzureVM](.\Get-AzureVM.md)

