---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: AAFAAED5-32CA-470E-BF38-00B06DA56BA3
online version: 
schema: 2.0.0
---

# Disable-AzureRmVMDiskEncryption

## SYNOPSIS
Disables encryption on an IaaS Windows virtual machine.

## SYNTAX

```
Disable-AzureRmVMDiskEncryption [-ResourceGroupName] <String> [-VMName] <String> [[-VolumeType] <String>]
 [[-Name] <String>] [[-TypeHandlerVersion] <String>] [-Force] [-DisableAutoUpgradeMinorVersion]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AzureRmVMDiskEncryption** cmdlet disables encryption on an infrastructure as a service (IaaS) Windows virtual machine.
This cmdlet is only supported for Windows virtual machines.  Running this cmdlet against a Linux virtual machine with an encrypted OS drive will not succeed and will render the Linux virtual machine inaccessible. 

This cmdlet installs an extension on the virtual machine to disable encryption.  If the *Name* parameter is not specified, the default extension will be used.  *Caution: This cmdlet reboots the virtual machine.*

## EXAMPLES

### Example 1: Disable encryption for all volumes on a Windows virtual machine
```
PS C:\>Disable-AzureRMVMDiskEncryption -ResourceGroupName "Group001" -VMName "VM002"
```

This command disables encryption for volumes of type all for the virtual machine named VM002 that belongs to the resource group named Group001.
Since the *VolumeType* parameter is not specified, the cmdlet sets the value to All.

### Example 2: Disable encryption for data volumes on a Windows virtual machine
```
PS C:\>$ResourceGroup = "Group002";
PS C:\> $VMName = "VM004";
PS C:\> Disable-AzureRMVMDiskEncryption -ResourceGroupName "Group002" -VMName "VM004" -VolumeType "Data"
```

This command disables encryption for volumes of type data for the virtual machine named VM004 that belongs to the resource group named Group002.

## PARAMETERS

### -DisableAutoUpgradeMinorVersion
Indicates that this cmdlet disables auto-upgrade of the minor version of the extension.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
ps_force

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Name
Specifes the name of the Azure Resource Manager (ARM) resource that represents the extension.
If this parameter is not specified, this cmdlet defaults to "AzureDiskEncryption for Windows VMs".

```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group name of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Specifies the version of the encryption extension.
If you do not specify a value for this parameter, the latest version of the extension is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine that this cmdlet disables encryption on.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumeType
Specifies the type of virtual machine volumes to perform the encryption operation.
For Windows virtual machines, valid values are: 

- All
- OS
- Data.
If you do not specify a value for this parameter, the default value is All.
Disable encryption is not currently supported for Linux.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AzureRmVMDiskEncryptionStatus](./Get-AzureRmVMDiskEncryptionStatus.md)

[Remove-AzureRmVMDiskEncryptionExtension](./Remove-AzureRmVMDiskEncryptionExtension.md)

[Set-AzureRmVMDiskEncryptionExtension](./Set-AzureRmVMDiskEncryptionExtension.md)


