---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureIPForwarding.md
schema: 2.0.0
---

# Set-AzureIPForwarding

## SYNOPSIS
Enables or disables IP forwarding.

## SYNTAX

### EnableIaaSIPForwardingParamSet
```
Set-AzureIPForwarding [-VM] <PersistentVMRoleContext> [-ServiceName] <String>
 [[-NetworkInterfaceName] <String>] [-Enable] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### DisableIaaSIPForwardingParamSet
```
Set-AzureIPForwarding [-VM] <PersistentVMRoleContext> [-ServiceName] <String>
 [[-NetworkInterfaceName] <String>] [-Disable] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### EnableSlotIPForwardingParamSet
```
Set-AzureIPForwarding [-ServiceName] <String> [[-Slot] <String>] [-RoleName] <String>
 [[-NetworkInterfaceName] <String>] [-Enable] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### DisableSlotIPForwardingParamSet
```
Set-AzureIPForwarding [-ServiceName] <String> [[-Slot] <String>] [-RoleName] <String>
 [[-NetworkInterfaceName] <String>] [-Disable] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureIPForwarding** cmdlet enables or disables IP forwarding for a virtual machine, for a platform as a service (PaaS) role, or a network adapter that belongs to a virtual machine or PaaS role.

## EXAMPLES

### Example 1: Enable IP forwarding for a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Set-AzureIPForwarding -Enable
```

This command gets a virtual machine named ContosoVM06 for the service named ContosoService, and passes that virtual machine object to the current cmdlet.
The current cmdlet enables IP forwarding for that virtual machine.

### Example 2: Disable IP forwarding for a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Set-AzureIPForwarding -Disable
```

This command gets a virtual machine named ContosoVM06 for the service named ContosoService, and passes that virtual machine object to the current cmdlet.
The current cmdlet disables IP forwarding for that virtual machine.

## PARAMETERS

### -Disable
Indicates that this cmdlet disables IP forwarding.

```yaml
Type: SwitchParameter
Parameter Sets: DisableIaaSIPForwardingParamSet, DisableSlotIPForwardingParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates that this cmdlet enables IP forwarding.

```yaml
Type: SwitchParameter
Parameter Sets: EnableIaaSIPForwardingParamSet, EnableSlotIPForwardingParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterfaceName
Specifies the name of the network adapter on which this cmdlet sets IP forwarding.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Specifies the name of a PaaS role on which this cmdlet sets IP forwarding.

```yaml
Type: String
Parameter Sets: EnableSlotIPForwardingParamSet, DisableSlotIPForwardingParamSet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of a cloud service.
The PaaS role belongs to the service that this parameter specifies.

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

### -Slot
Specifies a PaaS slot.
The PaaS role for which this cmdlet sets forwarding has the slot that this parameter specifies.
Valid values are: 

- Production
- Staging 

The default value is Production.

```yaml
Type: String
Parameter Sets: EnableSlotIPForwardingParamSet, DisableSlotIPForwardingParamSet
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object on which this cmdlet sets IP forwarding.

```yaml
Type: PersistentVMRoleContext
Parameter Sets: EnableIaaSIPForwardingParamSet, DisableIaaSIPForwardingParamSet
Aliases: 

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

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzureIPForwarding](.\Get-AzureIPForwarding.md)

