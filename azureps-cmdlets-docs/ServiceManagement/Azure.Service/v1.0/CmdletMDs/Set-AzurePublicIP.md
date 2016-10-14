---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzurePublicIP.md
schema: 2.0.0
---

# Set-AzurePublicIP

## SYNOPSIS
Adds a Public IP to an azure_2 virtual machine.

## SYNTAX

```
Set-AzurePublicIP [-PublicIPName] <String> [[-IdleTimeoutInMinutes] <Int32>] [[-DomainNameLabel] <String>]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzurePublicIP** cmdlet adds a Public IP to an azure_2 virtual machine.
If you run this cmdlet for an existing virtual machine, update the virtual machine to implement your changes.
You can specify a domain name label to create a corresponding DNS entry for the public IP.

## EXAMPLES

### Example 1: Add a Public IP to an existing virtual machine
```
PS C:\>Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" | Update-AzureVM
```

This command gets the virtual machine named FTPInstance in the service named FTPInAzure by using the Get-AzureVM cmdlet.
The command passes that virtual machine to the current cmdlet by using the pipeline operator.
The current cmdlet adds the Public IP name ftpip.
The command passes the virtual machine to the Update-AzureVM cmdlet, which implements your changes.

### Example 2: Add a Public IP to a new virtual machine
```
PS C:\>New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

This command creates a virtual machine configuration object by using the New-AzureVMConfig cmdlet.
The command passes that object to the Add-AzureProvisioningConfig cmdlet, which provides additional configuration.
The current cmdlet adds the Public IP name ftpip.
The command passes the configuration to the New-AzureVM cmdlet, which creates the virtual machine.

### Example 3: Add a Public IP and label to an existing virtual machine
```
PS C:\>Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | Update-AzureVM
```

This command gets the virtual machine named FTPInstance in the service named FTPInAzure by using the Get-AzureVM cmdlet.
The command passes that virtual machine to the current cmdlet by using the pipeline operator.
The current cmdlet adds the Public IP name ftpip and the label ipname.
The command updates the virtual machine, which implements your changes.

### Example 4: Add a Public IP and label to a new virtual machine
```
PS C:\>New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName $images[50].ImageName | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

This command creates a virtual machine configuration object, and then passes that object to **Add-AzureProvisioningConfig**, which provides additional configuration.
The current cmdlet adds the Public IP name ftpip and the label ipname.
The command creates the virtual machine.

## PARAMETERS

### -PublicIPName
Specifies the Public IP name.

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

### -IdleTimeoutInMinutes
Specifies the TCP idle time-out period in minutes.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNameLabel
Specifies the name to use for a corresponding DNS entry for the public IP address.

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

### -VM
Specifies the virtual machine to which this cmdlet adds Public IP.

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
ps_azureprofile_description

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

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.ServiceManagement.Model.IPersistentVM

## NOTES

## RELATED LINKS

[Get-AzurePublicIP](.\Get-AzurePublicIP.md)

[Get-AzureVM](.\Get-AzureVM.md)

[New-AzureVM](.\New-AzureVM.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

[Remove-AzurePublicIP](.\Remove-AzurePublicIP.md)

[Update-AzureVM](.\Update-AzureVM.md)

