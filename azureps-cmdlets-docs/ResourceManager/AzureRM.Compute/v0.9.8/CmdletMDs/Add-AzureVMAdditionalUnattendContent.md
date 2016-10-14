---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureAvailabilitySet.md
schema: 2.0.0
---

# Add-AzureVMAdditionalUnattendContent

## SYNOPSIS
Adds information to the unattended Windows Setup answer file.

## SYNTAX

```
Add-AzureVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>] [[-SettingName] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureVMAdditionalUnattendContent** cmdlet adds information to the unattended Windows Setup answer file.
Specify additional base 64 encoded XML formatted information that this cmdlet adds to the unattend.xml file.

## EXAMPLES

### Example 1: Add content to unattend.xml
```
PS C:\>$AvailabilitySet = Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzureVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
PS C:\> $VirtualMachine = Add-AzureVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

The first command gets the availability set named AvailablitySet03 in the resource group named ResourceGroup11, and then stores that object in the $AvailabilitySet variable.

The second command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.
The virtual machine belongs to the availability set stored in $AvailabilitySet.

The third command creates a credential object by using the **Get-Credential** cmdlet, and then stores the result in the $Credential variable.
The command prompts you for a user name and password.
For more information, type `Get-Help Get-Credential`.

The fourth command uses the **Set-AzureVMOperatingSystem** cmdlet to configure the virtual machine stored in $VirtualMachine.

The fifth command assigns content to the $AucContent variable.
The content includes a password.

The final command adds the content stored in $AucContent to the unattend.xml file.

## PARAMETERS

### -Content
Specifies base 64 encoded XML formatted content.
This cmdlet adds the content to the unattend.xml file.
The XML content must be less than 4 KB and must include the root element for the setting or feature that this cmdlet inserts.

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

### -SettingName
Specifies the name of the setting to which the content applies.
Valid values are: 

- FirstLogonCommands
- AutoLogon

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object that this cmdlet modifies.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.
Create a virtual machine object by using the **New-AzureVMConfig** cmdlet.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 1
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

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

[Set-AzureVMOperatingSystem](.\Set-AzureVMOperatingSystem.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

