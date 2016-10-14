---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureNetworkSecurityGroupAssociation.md
schema: 2.0.0
---

# Remove-AzureNetworkSecurityGroupAssociation

## SYNOPSIS
Removes a network security group.

## SYNTAX

### RemoveNetworkSecurityGroupAssociationFromSubnet
```
Remove-AzureNetworkSecurityGroupAssociation [-Name] <String> [-VirtualNetworkName] <String>
 [-SubnetName] <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

### RemoveNetworkSecurityGroupAssociationFromIaaSRole
```
Remove-AzureNetworkSecurityGroupAssociation [-Name] <String> [-VM] <PersistentVMRoleContext>
 [-ServiceName] <String> [[-NetworkInterfaceName] <String>] [-Force] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### RemoveNetworkSecurityGroupAssociationFromPaaSRole
```
Remove-AzureNetworkSecurityGroupAssociation [-Name] <String> [[-Slot] <String>] [-RoleName] <String>
 [-ServiceName] <String> [[-NetworkInterfaceName] <String>] [-Force] [-PassThru] [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureNetworkSecurityGroupAssociation** cmdlet removes a network security group from a virtual machine.

## EXAMPLES

### Example 1: Remove a virtual machine to a network security group
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Remove-AzureNetworkSecurityGroupAssociation -Name "ContosoNetworkSecurityGroup"
```

This command gets a virtual machine named ContosoVM06 for the service named ContosoService, and passes that virtual machine object to the current cmdlet.
The current cmdlet removes the network security group named ContosoNetworkSecurityGroup from that virtual machine.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies the name of the network security group that this cmdlet removes.

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

### -NetworkInterfaceName
Specifies the name of the network adapter from which this cmdlet removes the network security group.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole, RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: False
Position: 5
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
Specifies the name of a PaaS role from which this cmdlet removes the network security group.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of a cloud service.
The PaaS role from which this cmdlet removes a network security group belongs to the service that this parameter specifies.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole, RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies a PaaS slot.
The PaaS role from which this cmdlet removes a network security group has the slot that this parameter specifies.
Valid values are: 

- Production
- Staging 

The default value is Production.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of a subnet from which this cmdlet removes the network security group.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromSubnet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Specifies the name of a virtual network that contains the subnet from which this cmdlet removes the network security group.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromSubnet
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
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

[Set-AzureNetworkSecurityGroupAssociation](.\Set-AzureNetworkSecurityGroupAssociation.md)

