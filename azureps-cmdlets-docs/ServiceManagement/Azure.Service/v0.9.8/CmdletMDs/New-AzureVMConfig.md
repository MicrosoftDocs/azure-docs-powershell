---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 2c5c7142-218d-46ac-8faf-54d0deb28f13
schema: 2.0.0
---

# New-AzureVMConfig

## SYNOPSIS
Creates an Azure virtual machine configuration object.

## SYNTAX

### ImageName (Default)
```
New-AzureVMConfig [-Name] <String> [-InstanceSize] <String> [[-HostCaching] <String>]
 [[-AvailabilitySetName] <String>] [[-Label] <String>] [-ImageName] <String> [-MediaLocation <String>]
 [[-DiskLabel] <String>] [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### DiskName
```
New-AzureVMConfig [-Name] <String> [-InstanceSize] <String> [[-HostCaching] <String>]
 [[-AvailabilitySetName] <String>] [[-Label] <String>] [-DiskName] <String> [-Profile <AzureProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVMConfig** cmdlet creates an Azure  virtual machine configuration object.
You can use this object to perform a new deployment and add a new virtual machine to an existing deployment.

## EXAMPLES

### Example 1: Create a Windows virtual machine configuration
```
PS C:\>$Image = (Get-AzureVMImage)[4].ImageName 
C:\PS> New-AzureVMConfig -Name "MyVM1" -InstanceSize ExtraSmall -ImageName $Image | Add-AzureProvisioningConfig -Windows -Password $AdminPassword | Add-AzureDataDisk -CreateNew -DiskSizeInGB 50 -DiskLabel "Datadisk1" -LUN 0 | New-AzureVM  ¢â‚�?ServiceName "MySvc1"
```

This command creates a Windows virtual machine configuration with operating system disk, data disk and provisioning configuration.
This configuration is then used to create a new virtual machine.

### Example 2: Create a Linux virtual machine configuration
```
PS C:\>$Image = (Get-AzureVMImage)[7].ImageName
C:\PS> New-AzureVMConfig -Name "MyVM1" -InstanceSize ExtraSmall -ImageName $Image | Add-AzureProvisioningConfig  ¢â‚�?Linux  ¢â‚�?LinuxUser $LinuxUser -Password $AdminPassword | Add-AzureDataDisk -CreateNew -DiskSizeInGB 50 -DiskLabel "Datadisk1" -LUN 0 | New-AzureVM  ¢â‚�?ServiceName "MySvc1"
```

This command creates a new Linux virtual machine configuration with operating system disk, data disk and provisioning configuration.
This configuration is then used to create a new virtual machine.

## PARAMETERS

### -AvailabilitySetName
Specifies the name of the availability set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskLabel
Specifies a label for the operating system disk.

```yaml
Type: String
Parameter Sets: ImageName
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskName
Specifies a name for the operating system disk.

```yaml
Type: String
Parameter Sets: DiskName
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostCaching
Specifies the host caching mode for the operating system disk.

Valid values are:

- ReadOnly
- ReadWrite

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the virtual machine image to use for the operating system disk.

```yaml
Type: String
Parameter Sets: ImageName
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceSize
Specifies the size of the instance.

The acceptable values for this parameter are:

- ExtraSmall
- Small
- Medium
- Large
- ExtraLarge
- A5
- A6
- A7
- A8
- A9
- Basic_A0
- Basic_A1
- Basic_A2
- Basic_A3
- Basic_A4
- Standard_D1
- Standard_D2
- Standard_D3
- Standard_D4
- Standard_D11
- Standard_D12
- Standard_D13
- Standard_D14

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label to assign to the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MediaLocation
Specifies the Azure storage location for the new virtual machine disk.

```yaml
Type: String
Parameter Sets: ImageName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine.

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

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Azure Service Cmdlets](.\Azure.Service.md)

