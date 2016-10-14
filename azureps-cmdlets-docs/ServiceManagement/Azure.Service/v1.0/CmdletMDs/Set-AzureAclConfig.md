---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureAclConfig.md
schema: 2.0.0
---

# Set-AzureAclConfig

## SYNOPSIS
Modifies an ACL configuration object.

## SYNTAX

### AddRule
```
Set-AzureAclConfig [-AddRule] [-Action] <String> [-RemoteSubnet] <String> [[-Order] <Int32>]
 [[-Description] <String>] -ACL <NetworkAclObject> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### RemoveRule
```
Set-AzureAclConfig [-RemoveRule] [-RuleId] <Int32> -ACL <NetworkAclObject>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### SetRule
```
Set-AzureAclConfig [-SetRule] [-RuleId] <Int32> [[-Action] <String>] [[-RemoteSubnet] <String>]
 [[-Order] <Int32>] [[-Description] <String>] -ACL <NetworkAclObject> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureAclConfig** cmdlet modifies an access control list (ACL) configuration object from an existing azure_2 virtual machine configuration.

## EXAMPLES

### Example 1: Add a rule to a new ACL configuration
```
PS C:\>$Acl = New-AzureAclConfig
PS C:\> Set-AzureAclConfig -AddRule -ACL $Acl -Action Permit -RemoteSubnet "172.0.0.0/8" -Order 100 -Description "Permit ACL rule"
```

The first command creates an ACL configuration, and then stores it in the $Acl variable.

The second command adds a new rule to the configuration stored in $Acl.
The command specifies an action, subnet, order, and description for the rule.

### Example 2: Modify a rule in an ACL configuration
```
PS C:\>$Acl = Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Get-AzureAclConfig -EndpointName "Web"
PS C:\> Set-AzureAclConfig -SetRule -RuleId 0 -ACL $Acl -Order 102 -Description "Web endpoint rule"
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Set-AzureEndpoint -ACL $Acl -Name "Web" | Update-AzureVM
```

The first command gets the virtual machine named VirtualMachine07 in the service named ContosoService by using the Get-AzureVM cmdlet.
The command passes that object to the Get-AzureAclConfig cmdlet by using the pipeline operator.
That cmdlet gets the ACL configuration for the endpoint named Web.
The command stores that ACL configuration object in the $Acl variable.

The second command modifies the rule that has the ID of 0.
The command changes the order and the description of the rule.

The final command sets the ACL configuration object for that virtual machine by using the Set-AzureEndpoint cmdlet.
The command also updates that virtual machine.

### Example 3: Remove a rule from an ACL configuration
```
PS C:\>$Acl = Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Get-AzureAclConfig -EndpointName "Web"
PS C:\> Set-AzureAclConfig -RemoveRule -ID 0 -ACL $Acl
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Set-AzureEndpoint -ACL $Acl -Name "Web" | Update-AzureVM
```

The first command stores an ACL configuration object in the $Acl variable.
This is the same as the previous example.

The second command removes the rule that has the ID 0 from the ACL configuration in $Acl.

The final command sets the ACL configuration object for the virtual machine and updates that virtual machine.
This is the same as the previous example.

## PARAMETERS

### -AddRule
Indicates that this cmdlet adds a rule to the ACL configuration.

```yaml
Type: SwitchParameter
Parameter Sets: AddRule
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Action
Specifies the action for the rule that this cmdlet adds or modifies.
Valid values are: Permit and Deny.

```yaml
Type: String
Parameter Sets: AddRule
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetRule
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteSubnet
Specifies the remote subnet for the rule that this cmdlet adds or modifies.
Specifies an address in Classless Interdomain Routing (CIDR) format.

```yaml
Type: String
Parameter Sets: AddRule
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetRule
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Order
Specifies the processing order for the rule that this cmdlet adds or modifies.

```yaml
Type: Int32
Parameter Sets: AddRule, SetRule
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the rule that this cmdlet adds or modifies.

```yaml
Type: String
Parameter Sets: AddRule, SetRule
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ACL
Specifies an ACL configuration object that this cmdlet modifies.

```yaml
Type: NetworkAclObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -RemoveRule
Indicates that this cmdlet removes a rule from the ACL configuration.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveRule
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleId
Specifies the ID of the rule that this cmdlet removes or modifies for the ACL configuration.

```yaml
Type: Int32
Parameter Sets: RemoveRule, SetRule
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetRule
Indicates that this cmdlet modifies a rule in the ACL configuration.

```yaml
Type: SwitchParameter
Parameter Sets: SetRule
Aliases: 

Required: True
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

[Get-AzureAclConfig](.\Get-AzureAclConfig.md)

[Get-AzureVM](.\Get-AzureVM.md)

[New-AzureAclConfig](.\New-AzureAclConfig.md)

[Remove-AzureAclConfig](.\Remove-AzureAclConfig.md)

[Set-AzureEndpoint](.\Set-AzureEndpoint.md)

[Update-AzureVM](.\Update-AzureVM.md)

