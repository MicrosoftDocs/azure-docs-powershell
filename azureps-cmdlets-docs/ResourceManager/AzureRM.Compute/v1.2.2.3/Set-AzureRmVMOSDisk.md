---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmVMOSDisk

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### DefaultParamSet (Default)
```
Set-AzureRmVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [-VhdUri] <String> [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [-CreateOption] <DiskCreateOptionTypes> [-DiskSizeInGB <Int32>]
 [<CommonParameters>]
```

### WindowsParamSet
```
Set-AzureRmVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [-VhdUri] <String> [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [-CreateOption] <DiskCreateOptionTypes> [-Windows] [-DiskSizeInGB <Int32>]
 [<CommonParameters>]
```

### WindowsDiskEncryptionParameterSet
```
Set-AzureRmVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [-VhdUri] <String> [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [-CreateOption] <DiskCreateOptionTypes> [-Windows]
 [-DiskEncryptionKeyUrl] <String> [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>]
 [[-KeyEncryptionKeyVaultId] <String>] [-DiskSizeInGB <Int32>] [<CommonParameters>]
```

### LinuxParamSet
```
Set-AzureRmVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [-VhdUri] <String> [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [-CreateOption] <DiskCreateOptionTypes> [-Linux] [-DiskSizeInGB <Int32>]
 [<CommonParameters>]
```

### LinuxDiskEncryptionParameterSet
```
Set-AzureRmVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [-VhdUri] <String> [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [-CreateOption] <DiskCreateOptionTypes> [-Linux] [-DiskEncryptionKeyUrl] <String>
 [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>] [[-KeyEncryptionKeyVaultId] <String>]
 [-DiskSizeInGB <Int32>] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Caching
The virtual machine OS disk's caching.

```yaml
Type: CachingTypes
Parameter Sets: (All)
Aliases: 
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreateOption
The virtual machine data disk's create option.

```yaml
Type: DiskCreateOptionTypes
Parameter Sets: (All)
Aliases: 
Accepted values: FromImage, Empty, Attach

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskEncryptionKeyUrl
the URL referencing a secret in a disk encryption key vault

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskEncryptionKeyVaultId
the Id of a disk encryption key vault

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: True
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskSizeInGB
The virtual machine OS disk's size in GB.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyEncryptionKeyUrl
the URL referencing a key in a key encryption key vault

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyEncryptionKeyVaultId
the Id of a key encryption key Vault

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
The virtual machine disk's OS is Linux.

```yaml
Type: SwitchParameter
Parameter Sets: LinuxParamSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The virtual machine OS disk's name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OSDiskName, DiskName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImageUri
The virtual machine OS disk's source image Uri.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdUri
The virtual machine OS disk's Vhd Uri.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OSDiskVhdUri, DiskVhdUri

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
The virtual machine profile.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Windows
The virtual machine disk's OS is Windows.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsParamSet, WindowsDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
System.String
System.Nullable`1[[Microsoft.Azure.Management.Compute.Models.CachingTypes, Microsoft.Azure.Management.Compute, Version=10.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]
Microsoft.Azure.Management.Compute.Models.DiskCreateOptionTypes
System.Management.Automation.SwitchParameter
System.Nullable`1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

