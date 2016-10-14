---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: .\Add-AzureDnsRecordConfig.md
schema: 2.0.0
---

# Remove-AzureDnsRecordConfig

## SYNOPSIS
Removes a DNS record from a record set.

## SYNTAX

### A
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv4Address <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### AAAA
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv6Address <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### NS
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Nsdname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### MX
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Exchange <String> -Preference <UInt16>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### PTR
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ptrdname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### TXT
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Value <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SRV
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Priority <UInt16> -Target <String> -Port <UInt16>
 -Weight <UInt16> [-Profile <AzureProfile>] [<CommonParameters>]
```

### CNAME
```
Remove-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Cname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDnsRecordConfig** cmdlet removes a Domain Name System (DNS) record from a record set.
The **RecordSet** object is an offline object, and changes to it do not change the DNS responses until after you run the **Set-AzureDnsRecordSet** cmdlet to persist the change to the Microsoft Azure DNS service.

To remove a record, all the fields for that record type must match exactly.
You cannot add or remove SOA records.

You can pass the **RecordSet** object to this cmdlet as a parameter or by using the pipeline operator.

## EXAMPLES

### Example 1: Remove A records
```
PS C:\>$RecordSet = Remove-AzureDnsRecordConfig -RecordSet $RecordSet -Ipv4Address "172.16.0.0"
```

This command removes the A records with the specified IP address from the record set stored in $RecordSet.

### Example 2: Remove specified SRV records
```
PS C:\>$RecordSet = Remove-AzureDnsRecordConfig -Port 8080 -Priority 0 -RecordSet $RecordSet -Target "target.example.com" -Weight 5
```

This command removes SRV records from the $RecordSet variable where Port=8080, Priority=0, Weight=5, and Target=target.example.com.

## PARAMETERS

### -Cname
Specifies the domain name for a CNAME record.

```yaml
Type: String
Parameter Sets: CNAME
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exchange
Specifies the mail exchange server name for an MX record.

```yaml
Type: String
Parameter Sets: MX
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ipv4Address
Specifies an IPv4 address for an A record.

```yaml
Type: String
Parameter Sets: A
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ipv6Address
Specifies an IPv6 address for an AAAA record.

```yaml
Type: String
Parameter Sets: AAAA
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nsdname
Specifies the name server for an NS record.

```yaml
Type: String
Parameter Sets: NS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Specifies the port for an SRV record.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Preference
Specifies the preference for an MX record.

```yaml
Type: UInt16
Parameter Sets: MX
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Priority
Specifies the priority for an SRV record.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the domain name for a CNAME record.

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

### -Ptrdname
Specifies the DNAME of a PTR record.

```yaml
Type: String
Parameter Sets: PTR
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordSet
Specifies the **RecordSet** that contains the record to remove.

```yaml
Type: DnsRecordSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Target
Specifies the target for an SRV record.

```yaml
Type: String
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Specifies the value for a TXT record.

```yaml
Type: String
Parameter Sets: TXT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Weight
Specifies the weight for an SRV record.

```yaml
Type: UInt16
Parameter Sets: SRV
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

### Microsoft.Azure.Commands.Dns.DnsRecordSet
You can pipe a **DnsRecordSet** object to this cmdlet.
This is an offline representation of the record set and updates to it do not change DNS responses until after you run **Set-AzureDnsRecordSet**.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
This cmdlet returns the modified **RecordSet** object.

## NOTES

## RELATED LINKS

[Add-AzureDnsRecordConfig](.\Add-AzureDnsRecordConfig.md)

[Get-AzureDnsRecordSet](.\Get-AzureDnsRecordSet.md)

[Set-AzureDnsRecordSet](.\Set-AzureDnsRecordSet.md)

