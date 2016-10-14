---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# New-AzureVM

## SYNOPSIS
Creates a virtual machine.

## SYNTAX

```
New-AzureVM -ResourceGroupName <String> -Location <String> -VM <PSVirtualMachine> [-Tags <Hashtable[]>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVM** cmdlet creates a virtual machine in Azure.
This cmdlet takes a virtual machine object as input.
Use the **New-AzureVMConfig** cmdlet to create a virtual machine object.
Configure the virtual machine object by using other cmdlets, such as **Set-AzureVMOperatingSystem**, **Set-AzureVMSourceImage**, **Add-AzureVMNetworkInterface**, and **Set-AzureVMOSDisk**.

## EXAMPLES

### Example 1: Create a virtual machine
```
PS C:\># Variables    
## Global
$ResourceGroupName = "ResourceGroup11"
$Location = "westeurope"

## Storage
$StorageName = "GeneralStorage6cc"
$StorageType = "Standard_GRS"

## Network
$InterfaceName = "ServerInterface06"
$Subnet1Name = "Subnet1"
$VNetName = "VNet09"
$VNetAddressPrefix = "10.0.0.0/16"
$VNetSubnetAddressPrefix = "10.0.0.0/24"

## Compute
$VMName = "VirtualMachine12"
$ComputerName = "Server22"
$VMSize = "Standard_A2"
$OSDiskName = $VMName + "osDisk"

# Resource Group
New-AzureResourceGroup -Name $ResourceGroupName -Location $Location

# Storage
$StorageAccount = New-AzureStorageAccount -ResourceGroupName $ResourceGroupName -Name $StorageName -Type $StorageType -Location $Location

# Network
$PIp = New-AzurePublicIpAddress -Name $InterfaceName -ResourceGroupName $ResourceGroupName -Location $Location -AllocationMethod Dynamic
$SubnetConfig = New-AzureVirtualNetworkSubnetConfig -Name $Subnet1Name -AddressPrefix $VNetSubnetAddressPrefix
$VNet = New-AzureVirtualNetwork -Name $VNetName -ResourceGroupName $ResourceGroupName -Location $Location -AddressPrefix $VNetAddressPrefix -Subnet $SubnetConfig
$Interface = New-AzureNetworkInterface -Name $InterfaceName -ResourceGroupName $ResourceGroupName -Location $Location -SubnetId $VNet.Subnets[0].Id -PublicIpAddressId $PIp.Id

# Compute

## Setup local VM object
$Credential = Get-Credential
$VirtualMachine = New-AzureVMConfig -VMName $VMName -VMSize $VMSize
$VirtualMachine = Set-AzureVMOperatingSystem -VM $VirtualMachine -Windows -ComputerName $ComputerName -Credential $Credential -ProvisionVMAgent -EnableAutoUpdate
$VirtualMachine = Set-AzureVMSourceImage -VM $VirtualMachine -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2012-R2-Datacenter -Version "latest"
$VirtualMachine = Add-AzureVMNetworkInterface -VM $VirtualMachine -Id $Interface.Id
$OSDiskUri = $StorageAccount.PrimaryEndpoints.Blob.ToString() + "vhds/" + $OSDiskName + ".vhd"
$VirtualMachine = Set-AzureVMOSDisk -VM $VirtualMachine -Name $OSDiskName -VhdUri $OSDiskUri -CreateOption FromImage

## Create the VM in Azure
New-AzureVM -ResourceGroupName $ResourceGroupName -Location $Location -VM $VirtualMachine
```

This example script shows how to create a virtual machine.
This script uses several other cmdlets.

## PARAMETERS

### -Location
Specifies a location for the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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
Specifies the name of a resource group.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
@{Text=}```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies a local virtual machine to create. To obtain a virtual machine object, use the New-AzureVMConfig cmdlet. Configure the virtual machine by using other cmdlets, such as Set-AzureVMOperatingSystem, Set-AzureVMSourceImage, and Add-AzureVMNetworkInterface.```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureVM](.\Remove-AzureVM.md)

[Restart-AzureVM](.\Restart-AzureVM.md)

[Start-AzureVM](.\Start-AzureVM.md)

[Stop-AzureVM](.\Stop-AzureVM.md)

[Update-AzureVM](.\Update-AzureVM.md)

[Add-AzureVMDataDisk](.\Add-AzureVMDataDisk.md)

[Add-AzureVMNetworkInterface](.\Add-AzureVMNetworkInterface.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

[Set-AzureVMOperatingSystem](.\Set-AzureVMOperatingSystem.md)

[Set-AzureVMSourceImage](.\Set-AzureVMSourceImage.md)

[Set-AzureVMOSDisk](.\Set-AzureVMOSDisk.md)

