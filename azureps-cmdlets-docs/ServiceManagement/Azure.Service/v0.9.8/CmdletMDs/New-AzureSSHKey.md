---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureProvisioningConfig.md
schema: 2.0.0
---

# New-AzureSSHKey

## SYNOPSIS
Creates a SSH Key object to insert an existing certificate into a new Linux-based Azure virtual machines.

## SYNTAX

### keypair
```
New-AzureSSHKey [-KeyPair] [-Fingerprint] <String> [-Path] <String> [<CommonParameters>]
```

### publickey
```
New-AzureSSHKey [-PublicKey] [-Fingerprint] <String> [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSSHKey** cmdlet creates an SSH Key object for a certificate that has already been added to Azure.
This SSH Key object can then be used by **New-AzureProvisioningConfig** when creating the configuration object for a new virtual machine using **New-AzureVM**, or when creating a new virtual machine with **New-AzureQuickVM**.
When included as part of a virtual machine creation script, this adds the specified SSH Public Key or Key Pair to the new virtual machine.

## EXAMPLES

### Example 1: Create a certificate setting object
```
PS C:\>$myLxCert = New-AzureSSHKey -Fingerprint "D7BECD4D63EBAF86023BB4F1A5FBF5C2C924902A" -Path "/home/username/.ssh/authorized_keys"
```

This command creates a certificate setting object for an existing certificate and then stores the object in a variable for later use.

### Example 2: Add a certificate to a service
```
PS C:\>Add-AzureCertificate -ServiceName "MySvc" -CertToDeploy "C:\temp\MyLxCert.cer"
$myLxCert = New-AzureSSHKey ?Fingerprint "D7BECD4D63EBAF86023BB4F1A5FBF5C2C924902A" -Path "/home/username/.ssh/authorized_keys"
New-AzureVMConfig -Name "MyVM2" -InstanceSize Small -ImageName $LxImage `
          | Add-AzureProvisioningConfig -Linux -LinuxUser $lxUser -SSHPublicKeys $myLxCert -Password 'pass@word1' `
          | New-AzureVM -ServiceName "MySvc"
```

This command adds a certificate to an Azure service, and then creates a new Linux virtual machine that uses the certificate.

## PARAMETERS

### -KeyPair
Specifies that this cmdlet creates an object for inserting an SSH Key Pair into the new virtual machine configuration.

```yaml
Type: SwitchParameter
Parameter Sets: keypair
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fingerprint
Specifies the fingerprint of the certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to store the SSH Public Key or Key Pair.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicKey
Specifies that this cmdlet creates an object for inserting an SSH Public Key into the new virtual machine configuration.

```yaml
Type: SwitchParameter
Parameter Sets: publickey
Aliases: 

Required: True
Position: 0
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

[Add-AzureProvisioningConfig](.\Add-AzureProvisioningConfig.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

[New-AzureVM](.\New-AzureVM.md)

[New-AzureQuickVM](.\New-AzureQuickVM.md)

