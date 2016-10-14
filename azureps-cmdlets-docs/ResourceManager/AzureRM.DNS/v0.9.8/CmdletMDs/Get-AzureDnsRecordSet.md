---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: .\New-AzureDnsRecordSet.md
schema: 2.0.0
---

# Get-AzureDnsRecordSet

## SYNOPSIS
Gets a DNS record set.

## SYNTAX

### Object
```
Get-AzureDnsRecordSet [-Name <String>] -Zone <DnsZone> [-RecordType <String>] [-EndsWith <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Fields
```
Get-AzureDnsRecordSet [-Name <String>] -ZoneName <String> -ResourceGroupName <String> [-RecordType <String>]
 [-EndsWith <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDnsRecordSet** cmdlet gets the Domain Name System (DNS) record set with the specified name and type, in the specified zone.
If you do not specify the *Name* parameter, this cmdlet returns all record sets of the specified type in the zone.

If you do not specify the *RecordType* parameter, this cmdlet returns record sets of all types.

You can use the pipeline operator to pass a **DnsZone** object to this cmdlet, or you can pass a **DnsZone** object as the *Zone* parameter, or alternatively you can specify the zone by name.

## EXAMPLES

### Example 1: Get record sets with a specified name and type
```
PS C:\>$RecordSet = Get-AzureDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "www" -RecordType A
```

This command gets the record set of record type A named www in the specified resource group and zone, and then stores it in the $RecordSet variable.
Because the *RecordType* parameter is specified, only one **RecordSet** object is returned.

### Example 2: Get record sets of a specified type
```
PS C:\>$RecordSet = Get-AzureDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -RecordType A
```

This command gets all of record sets of record type A in the resource group named MyResourceGroup in the zone named myzone.com, and then stores them in the $RecordSet variable.

### Example 3: Get record sets with a specified name
```
PS C:\>$RecordSet = Get-AzureDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
```

This command gets all of the record sets named www in the resource group named MyResourceGroup in the zone named myzone.com, and then stores them in the $RecordSet variable.

## PARAMETERS

### -EndsWith
Specifies a suffix to use as a filter when you get multiple record sets.

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

### -Name
Specifies the name of the **RecordSet** to get.
If you do not specify the *Name* parameter, all record sets of the specified type are returned.

```yaml
Type: String
Parameter Sets: Object
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Fields
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

### -RecordType
Specifies the type of DNS record to get.
Valid values are: 

- A 
- AAAA 
- CNAME 
- MS 
- NS 
- PTR 
- SOA
- SRV 
- TXT

If you do not specify the *RecordType* parameter, this cmdlet returns record sets of all types.

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

### -ResourceGroupName
Specifies the resource group that contains the DNS zone.

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

### -Zone
Specifies the DNS zone that contains the record set to get.

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

### -ZoneName
Specifies the name of the DNS zone that contains the record set to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
You can pipe a **DnsZone** object to this cmdlet.
The **DnsZone** object represents the zone in which to look for the **RecordSet** object.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
This cmdlet returns one or more objects that represents the record sets that are found.
There will be at most one **RecordSet** returned if the *Name* and *RecordType* are specified, otherwise multiple **RecordSet** objects are returned as an array.

## NOTES

## RELATED LINKS

[New-AzureDnsRecordSet](.\New-AzureDnsRecordSet.md)

[Remove-AzureDnsRecordSet](.\Remove-AzureDnsRecordSet.md)

[Set-AzureDnsRecordSet](.\Set-AzureDnsRecordSet.md)

