---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureNetworkSecurityGroupAssociation.md
schema: 2.0.0
---

# Set-AzureNetworkSecurityGroupAssociation

## SYNOPSIS
Associates a network security group to a virtual machine, PaaS role, or network adapter.

## SYNTAX

### AddNetworkSecurityGroupAssociationToSubnet
```
Set-AzureNetworkSecurityGroupAssociation [-Name] <String> [-Force] [-PassThru] [-VirtualNetworkName] <String>
 [-SubnetName] <String> [-Profile <AzureSMProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### AddNetworkSecurityGroupAssociationToIaaSRole
```
Set-AzureNetworkSecurityGroupAssociation [-Name] <String> [-Force] [-PassThru] [-VM] <PersistentVMRoleContext>
 [-ServiceName] <String> [[-NetworkInterfaceName] <String>] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### AddNetworkSecurityGroupAssociationToPaaSRole
```
Set-AzureNetworkSecurityGroupAssociation [-Name] <String> [-Force] [-PassThru] [[-Slot] <String>]
 [-RoleName] <String> [-ServiceName] <String> [[-NetworkInterfaceName] <String>] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureNetworkSecurityGroupAssociation** cmdlet associates a network security group to a virtual machine, platform as a service (PaaS) role, or network adapter.

## EXAMPLES

### Example 1: Assign a virtual machine to a network security group
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Set-AzureNetworkSecurityGroupAssociation -Name "ContosoNetworkSecurityGroup"
```

This command gets a virtual machine named ContosoVM06 for the service named ContosoService, and passes that virtual machine object to the current cmdlet.
The current cmdlet assigns the network security group named ContosoNetworkSecurityGroup to that virtual machine.

## PARAMETERS

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

### -Name
Specifies the name of the network security group that this cmdlet sets.

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

### -NetworkInterfaceName
Specifies the name of the network adapter to which this cmdlet applies the network security group.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToIaaSRole, AddNetworkSecurityGroupAssociationToPaaSRole
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
passthru

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

### -RoleName
Specifies the name of a PaaS role to which this cmdlet applies the network security group.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToPaaSRole
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of a cloud service.
The PaaS role belongs to the service that this parameter specifies.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToIaaSRole, AddNetworkSecurityGroupAssociationToPaaSRole
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies a PaaS slot.
The PaaS role for which this cmdlet sets the network security group has the slot that this parameter specifies.
Valid values are: 

- Production
- Staging 

The default value is Production.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToPaaSRole
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of a subnet to which this cmdlet associates the network security group.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToSubnet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Specifies the name of a virtual network that contains the subnet to which this cmdlet associates the network security group.

```yaml
Type: String
Parameter Sets: AddNetworkSecurityGroupAssociationToSubnet
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to which this cmdlet applies the network security group.

```yaml
Type: PersistentVMRoleContext
Parameter Sets: AddNetworkSecurityGroupAssociationToIaaSRole
Aliases: 

Required: True
Position: 2
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

[Get-AzureNetworkSecurityGroupAssociation](.\Get-AzureNetworkSecurityGroupAssociation.md)

[Remove-AzureNetworkSecurityGroupAssociation](.\Remove-AzureNetworkSecurityGroupAssociation.md)

