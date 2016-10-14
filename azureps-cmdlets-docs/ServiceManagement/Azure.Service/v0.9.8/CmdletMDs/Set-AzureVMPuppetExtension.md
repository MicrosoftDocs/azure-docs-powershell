---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Set-AzureVMPuppetExtension

## SYNOPSIS
Sets the Puppet extension for a virtual machine.

## SYNTAX

```
Set-AzureVMPuppetExtension [-PuppetMasterServer] <String> [[-Version] <String>] [-Disable]
 [[-ReferenceName] <String>] -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMPuppetExtension** cmdlet sets the Puppet extension for a virtual machine.

## EXAMPLES

### Example 1: Set the Puppet extension for a virtual machine
```
PS C:\>Set-AzureVMPuppetExtension -VM $VM
```

This example sets the Puppet extension for the specified virtual machine as stored in the variable $VM.

## PARAMETERS

### -PuppetMasterServer
Specifies the fully qualified domain name (FQDN) of puppet master server.

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

### -Version
Specifies the extension version.

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

### -Disable
Indicates that this cmdlet disables the extension state.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferenceName
Specifies the reference name of the extension.

This is a user-defined string that is used to refer to an extension.
It is specified when the extension is added to the virtual machine for the first time.
For subsequent updates, you need to specify the previously used reference name when you update the extension.
The ReferenceName assigned to an extension is returned using the Get-AzureVM cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object.

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

[Get-AzureVM](.\Get-AzureVM.md)

