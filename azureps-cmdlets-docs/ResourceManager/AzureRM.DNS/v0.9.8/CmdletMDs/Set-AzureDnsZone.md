---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: http://azure.microsoft.com/en-us/documentation/articles/azure-preview-portal-using-tags/
schema: 2.0.0
---

# Set-AzureDnsZone

## SYNOPSIS
Updates a DNS zone.

## SYNTAX

### Fields
```
Set-AzureDnsZone -Name <String> -ResourceGroupName <String> [-Tag <Hashtable[]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Object
```
Set-AzureDnsZone -Zone <DnsZone> [-Overwrite] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureDnsZone** cmdlet updates the specified **DnsZone**.
This cmdlet does not update the **RecordSet** objects in the zone.
You can pass a **DnsZone** object as a parameter or by using the pipeline operator, or alternatively you can specify the zone by name.

## EXAMPLES

### Example 1: Update a DNS zone
```
PS C:\>$Zone = Get-AzureDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"  
PS C:\> $Zone.Tags = @(@{"Name"="Dept"; "Value"="Electrical"})
PS C:\> $Zone | Set-AzureDnsZone
```

The first command gets the zone named myzone.com from the specified resource group, and then stores it in the $Zone variable.

The second command updates the tags for $Zone.

The final command passes $Zone to the **Set-AzureDnsZone** cmdlet by using the pipeline operator.

### Example 2: Update tags for a zone
```
PS C:\>Set-AzureDNSZone -ResourceGroupName "MyResourceGroup" -Name "myzone.com" -Tag @(@{"Name"="Dept"; "Value"="Electrical"})
```

This command updates the tags for the zone named myzone.com without first explicitly getting the zone.

## PARAMETERS

### -Name
Specifies the name of the DNS zone to update.

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Overwrite
Indicates that this cmdlet ignores the Etag when deleting the record set, and that the record set is deleted even if it has changed since the last Get.

```yaml
Type: SwitchParameter
Parameter Sets: Object
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### -ResourceGroupName
Specifies the name of the resource group that contains the zone to update.

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies an array of tags to associate with the DNS zone.
Tags are name-value pairs that are represented as hashtables, for example, @(@{"Name"="dept"; "Value"="shopping"}, @{"Name"="env"; "Value"="production"})

```yaml
Type: Hashtable[]
Parameter Sets: Fields
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Specifies the DNS zone to update.

```yaml
Type: DnsZone
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
You can pipe a **DnsZone** object to this cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
This cmdlet returns a **DnsZone** object that represents the updated DNS zone with a new Etag.

## NOTES

## RELATED LINKS

[Using tags to organize your Azure resources](http://azure.microsoft.com/en-us/documentation/articles/azure-preview-portal-using-tags/)

[Get-AzureDnsZone](.\Get-AzureDnsZone.md)

[New-AzureDnsZone](.\New-AzureDnsZone.md)

[Remove-AzureDnsZone](.\Remove-AzureDnsZone.md)

