---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmPublicIpAddress

## SYNOPSIS
Creates a public IP address.

## SYNTAX

```
New-AzureRmPublicIpAddress [-Name <String>] -ResourceGroupName <String> [-Location <String>]
 -AllocationMethod <String> [-DomainNameLabel <String>] [-ReverseFqdn <String>] [-IdleTimeoutInMinutes <Int32>]
 [-Tag <Hashtable[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmPublicIpAddress cmdlet creates a public IP address.

## EXAMPLES

### --------------------------  1: Create a new public IP address.  --------------------------
@{paragraph=PS C:\\\>}





```
$publicIp = New-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName `
    -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location
```

This command creates a new public IP address resource.
A DNS record is created for $dnsPrefix.$location.cloudapp.azure.com pointing to the public IP address of this resource.
A public IP address is immediately allocated to this resource as the -AllocationMethod is specified as 'Static'.
If it is specified as 'Dynamic', a public IP address gets allocated only when you start (or create) the associated resource (like a VM or load balancer).

### --------------------------  2: Create a public IP address with a reverse FQDN  --------------------------
@{paragraph=PS C:\\\>}





```
$publicIp = New-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName `
    -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -ReverseFqdn $customFqdn
```

This command creates a new public IP address resource.
With the -ReverseFqdn parameter, Azure creates a DNS PTR record (reverse-lookup) for the public IP address allocated to this resource, pointing to the $customFqdn specified in the command.
As a pre-requisite, the $customFqdn (say webapp.contoso.com) should have a DNS CNAME record (forward-lookup) pointing to $dnsPrefix.$location.cloudapp.azure.com.

## PARAMETERS

### -Name
Specifies the name of the public IP address to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group in which to create a public IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the region in which to create a public IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllocationMethod
Specifies the method with which to allocate the public IP address.
The acceptable values for this parameter are:Static or Dynamic.
If it is specified as 'Static', a public IP address is immediately allocated.
If it is specified as 'Dynamic', a public IP address gets allocated only when you start (or create) the associated resource (like a VM or load balancer).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainNameLabel
Specifies the relative DNS name for a public IP address.
A DNS record is created for $DomainNameLabel.$location.cloudapp.azure.com pointing to the public IP address of this resource, if the FQDN is available.
If not, the command fails to create a public IP address resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseFqdn
Specifies a reverse fully qualified domain name (FQDN).
Azure creates a DNS PTR record (reverse-lookup) for the public IP address allocated to this resource, pointing to the FQDN specified by this parameter.
As a pre-requisite, the FQDN should have a DNS CNAME record (forward-lookup) pointing to $DomainNameLabel.$location.cloudapp.azure.com (where $DomainNameLabel is the value provided for -DomainNameLabel parameter).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Specifies the TCP idle time-out, in minutes.
This can be set for a duration between 4 and 30 minutes.
It works for inbound connections only.
For additional information on this, refer to https://azure.microsoft.com/en-us/documentation/articles/load-balancer-tcp-idle-timeout/.
Though this article refers to the setting in the context of Azure load balancer, it is applicable to the public IP address resource.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies a dictionary of tags to associate with a public IP address.

```yaml
Type: Hashtable[]
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
Type: SwitchParameter
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
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmPublicIpAddress]()

[Remove-AzureRmPublicIpAddress]()

[Set-AzureRmPublicIpAddress]()

