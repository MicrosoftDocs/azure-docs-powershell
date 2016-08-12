---
external help file: SMAzure_Compute.xml
online version: 4b060a7d-da50-45ff-adb6-bcba63faa90b
schema: 2.0.0
---

# New-WAPackVM
## SYNOPSIS
Creates a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-WAPackVM [-ProductKey <String>] [-VNet <VMNetwork>] -Name <String> -Template <VMTemplate>
 -VMCredential <PSCredential> [-Windows]
```

### UNNAMED_PARAMETER_SET_2
```
New-WAPackVM [-AdministratorSSHKey <String>] [-VNet <VMNetwork>] [-Linux] -Name <String> -Template <VMTemplate>
 -VMCredential <PSCredential>
```

### UNNAMED_PARAMETER_SET_3
```
New-WAPackVM [-VNet <VMNetwork>] -Name <String> -OSDisk <VirtualHardDisk> -VMSizeProfile <HardwareProfile>
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  Azure WAPack Cmdletshttp://msdn.microsoft.com/library/dn776450.aspx.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The New-WAPackVM cmdlet creates a virtual machine.

## EXAMPLES

### Example 1: Create a virtual machine for the Windows operating system by using a template
```
PS C:\>$Credentials = Get-Credential PS C:\> $Template = Get-WAPackVMTemplate -Name "ContosoTemplate04"PS C:\> New-WAPackVM -Name "ContosoV023" -Template $Template -VMCredential $Credentials -Windows
```

The first command creates a PSCredential object, and then stores it in the $Credentials variable.
The cmdlet prompts you for an account and password.
For more information, type Get-Help Get-Credential.

The second command gets the virtual machine template named ContosoTemplate04 by using the Get-WAPackVMTemplate cmdlet, and then stores it in the $Template variable.

The final command creates a virtual machine named ContosoV023, based on the template stored in the $Template variable.
The command specifies the Windows parameter, and, therefore, the virtual machine must run a version of the Windows operating system.

### Example 2: Create a virtual machine for the Linux operating system by using a template
```
PS C:\>$Credentials = Get-Credential PS C:\> $Template = Get-WAPackVMTemplate -Name "ContosoTemplate19"PS C:\> New-WAPackVM -Linux -Name "ContosoV028" -Template $Template -VMCredential $Credentials
```

The first command creates a PSCredential object, and then stores it in the $Credentials variable.

The second command gets the virtual machine template named ContosoTemplate19 by using the Get-WAPackVMTemplate cmdlet, and then stores it in the $Template variable.

The final command creates a virtual machine named ContosoV028, based on the template stored in the $Template variable.
The command specifies the Linux parameter, and, therefore, the virtual machine must run a version of the Linux operating system.

### Example 3: Create a virtual machine from an operating system disk and size profile
```
PS C:\>$OSDisk = Get-WAPackVMOSDisk -Name "ContosoDiskOS"PS C:\> $SizeProfile = Get-WAPackVMSizeProfile -Name "MediumSizeVM"PS C:\> New-WAPackVM -Name "ContosoV073" -OSDisk $OSDisk -VMSizeProfile $SizeProfile
```

The first command gets an operating system disk named ContosoDiskOS by using the Get-WAPackVMOSDisk cmdlet, and then stores it in the $OSDisk variable.

The second command gets the size profile named MediumSizeVM by using the Get-WAPackVMSizeProfile cmdlet, and then stores it in the $SizeProfile variable.

The final command creates a virtual machine named ContosoV073 from the operating system disk stored in $OSDisk and the size profile stored in $SizeProfile.

## PARAMETERS

### -AdministratorSSHKey
Specifies the Secure Shell (SSH) key for the Administrator account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Indicates that the cmdlet creates a virtual machine to run the Linux operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSDisk
Specifies an operating system disk as a VirtualHardDisk object.
To obtain an operating system disk, use the Get-WAPackVMOSDisk cmdlet.

```yaml
Type: VirtualHardDisk
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductKey
Specifies a product key.
The product key is a 25 digit number that identifies the product license.
Use a product key for an operating system that you plan to install on a virtual machine or host.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Template
Specifies a template.
The cmdlet creates a virtual machine based on the template that you specify.
To obtain a template object, use the Get-WAPackVMTemplate cmdlet.

```yaml
Type: VMTemplate
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMCredential
Specifies the credential for the local Administrator account.
To obtain a PSCredential object, use the Get-Credential cmdlet.
For more information, type Get-Help Get-Credential.

```yaml
Type: PSCredential
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSizeProfile
Specifies a size profile for a virtual machine as a HardwareProfile object.
To obtain a size profile, use the Get-WAPackVMSizeProfile cmdlet.

```yaml
Type: HardwareProfile
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VNet
Specifies a virtual network.
The cmdlet connects the virtual machine to the virtual network that you specify.
To obtain a virtual network, use the Get-WAPackVNet cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Windows
Indicates that the cmdlet creates a virtual machine to run the Windows operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVM](4b060a7d-da50-45ff-adb6-bcba63faa90b)

[Remove-WAPackVM](76b51795-43e6-45c3-ade1-aa8ea61efc23)

[Restart-WAPackVM](fd89742d-0d21-41e9-b3b1-5d8c638f8c6d)

[Resume-WAPackVM](d2594d2a-c0c6-4bca-8c81-9ed03b24d100)

[Set-WAPackVM](8b07e4cb-c677-4e6b-b034-25847da03dbf)

[Start-WAPackVM](8cc5bf6b-bf5b-427f-922d-57e4a99b2d55)

[Stop-WAPackVM](7f3e6c33-2196-4e24-95fd-e5763c6f7402)

[Suspend-WAPackVM](d8041113-5a71-447d-9bbe-dc6405aa6029)

[Get-WAPackVMSizeProfile](6dd436e0-b366-4a6b-adde-0aa6cdbfc3c6)

[Get-WAPackVMTemplate](1b16012f-1da0-42f0-8407-1601cf4168e8)

[Get-WAPackVMOSDisk](31ae72c2-c1d7-4c8d-b8be-61a46bfd6289)

[Get-WAPackVNe](3a6cfd0e-530b-42fb-a105-179559e91f3d)

