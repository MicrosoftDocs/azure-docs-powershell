---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 8D84F81A-F6B5-413D-B349-50947FCD5CFC
online version: https://learn.microsoft.com/powershell/module/az.network/new-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
---

# New-AzPublicIpAddress

## SYNOPSIS
Creates a public IP address.

## SYNTAX

```
New-AzPublicIpAddress [-Name <String>] -ResourceGroupName <String> -Location <String> [-EdgeZone <String>]
 [-Sku <String>] [-Tier <String>] -AllocationMethod <String> [-IpAddressVersion <String>]
 [-DomainNameLabel <String>] [-DomainNameLabelScope <PSDomainNameLabelScopeType>] [-IpTag <PSPublicIpTag[]>]
 [-PublicIpPrefix <PSPublicIpPrefix>] [-DdosProtectionMode <String>] [-DdosProtectionPlanId <String>]
 [-ReverseFqdn <String>] [-IdleTimeoutInMinutes <Int32>] [-Zone <String[]>] [-IpAddress <String>]
 [-Tag <Hashtable>] [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzPublicIpAddress** cmdlet creates a public IP address.

## EXAMPLES

### Example 1: Create a new public IP address
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location
```

This command creates a new public IP address resource.A DNS record is created for
$dnsPrefix.$location.cloudapp.azure.com pointing to the public IP address of this resource. A
public IP address is immediately allocated to this resource as the -AllocationMethod is specified
as 'Static'. If it is specified as 'Dynamic', a public IP address gets allocated only when you
start (or create) the associated resource (like a VM or load balancer).

### Example 2: Create a public IP address with a reverse FQDN
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -ReverseFqdn $customFqdn
```

This command creates a new public IP address resource. With the -ReverseFqdn parameter, Azure
creates a DNS PTR record (reverse-lookup) for the public IP address allocated to this resource,
pointing to the $customFqdn specified in the command. As a pre-requisite, the $customFqdn (say
webapp.contoso.com) should have a DNS CNAME record (forward-lookup) pointing to
$dnsPrefix.$location.cloudapp.azure.com.

### Example 3: Create a new public IP address with IpTag
```powershell
$ipTag = New-AzPublicIpTag -IpTagType "FirstPartyUsage" -Tag "/Sql"
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -IpTag $ipTag
```

This command creates a new public IP address resource.A DNS record is created for
$dnsPrefix.$location.cloudapp.azure.com pointing to the public IP address of this resource. A
public IP address is immediately allocated to this resource as the -AllocationMethod is specified
as 'Static'. If it is specified as 'Dynamic', a public IP address gets allocated only when you
start (or create) the associated resource (like a VM or load balancer). An Iptag is used to 
specific the Tags associated with resource. Iptag can be specified using New-AzPublicIpTag
and passed as input through -IpTags.

### Example 4: Create a new public IP address from a Prefix
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -PublicIpPrefix $publicIpPrefix -Sku Standard
```

This command creates a new public IP address resource. A DNS record is created for
$dnsPrefix.$location.cloudapp.azure.com pointing to the public IP address of this resource. A
public IP address is immediately allocated to this resource from the publicIpPrefix specified.
This option is only supported for the 'Standard' Sku and 'Static' AllocationMethod.

### Example 5: Create a specific public IP address from a BYOIP Prefix
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -Location $location -IpAddress 0.0.0.0 -PublicIpPrefix $publicIpPrefix -Sku Standard
```

This command creates a new public IP address resource with specific IP. NRP would check if the
given IP is inside the PublicIpPrefix and if the given PublicIpPrefix is BYOIP PublicIpPrefix.
the given public IP address is immediately allocated to this resource from the publicIpPrefix
specified. This option is only supported for the 'Standard' Sku and 'Static' AllocationMethod
and BYOIP PublicIpPrefix.

### Example 6: Create a new global public IP address
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $domainNameLabel -Location $location -Sku Standard -Tier Global
```

This command creates a new global public IP address resource.A DNS record is created for
$dnsPrefix.$location.cloudapp.azure.com pointing to the public IP address of this resource. A
global public IP address is immediately allocated to this resource.
This option is only supported for the 'Standard' Sku and 'Static' AllocationMethod.

### Example 7: Create a public IP address with a DomainNameLabelScope
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -DomainNameLabelScope $hasedReusePolicy -Location $location
```

This command creates a new public IP address resource. With the -DomainNameLabelScope parameter, Azure
creates a DNS record with a hashed value in FQDN for the public IP address allocated to this resource 
with the policy suggested by $hasedReusePolicy.

## PARAMETERS

### -AllocationMethod
Specifies the method with which to allocate the public IP address.
The acceptable values for this parameter are: Static or Dynamic.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Dynamic, Static

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Run cmdlet in the background

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DdosProtectionMode
The DdosProtectionMode to use for Public IP address

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: VirtualNetworkInherited, Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DdosProtectionPlanId
The DdosProtectionPlan id to attach to the Public IP address

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNameLabel
Specifies the relative DNS name for a public IP address.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainNameLabelScope
Specifies the HashedReusePolicy for DNS name for a public IP address.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.Network.Models.PSDomainNameLabelScopeType]
Parameter Sets: (All)
Aliases:
Accepted values: TenantReuse, SubscriptionReuse, ResourceGroupReuse, NoReuse

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EdgeZone
The name of the extended location.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Specifies the idle time-out, in minutes.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddress
Specifies the IP address when creating a BYOIP publicIpAddress.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddressVersion
Specifies the version of the IP address.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpTag
IpTag List.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpTag[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the region in which to create a public IP address.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the public IP address that this cmdlet creates.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpPrefix
Specifies the PSPublicIpPrefix from which to allocate the public IP address.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group in which to create a public IP address.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseFqdn
Specifies a reverse fully qualified domain name (FQDN).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
The public IP Sku name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, StandardV2

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Key-value pairs in the form of a hash table. For example:
@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tier
The public IP Sku Tier.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Regional, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
A list of availability zones denoting the IP allocated for the resource needs to come from.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSPublicIpTag[]

### Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix

### System.Int32

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## NOTES

## RELATED LINKS

[Get-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)

[Set-AzPublicIpAddress](./Set-AzPublicIpAddress.md)
