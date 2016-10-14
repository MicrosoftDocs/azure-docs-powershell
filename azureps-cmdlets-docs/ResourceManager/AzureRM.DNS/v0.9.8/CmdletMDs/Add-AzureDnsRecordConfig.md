---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: .\Get-AzureDnsRecordSet.md
schema: 2.0.0
---

# Add-AzureDnsRecordConfig

## SYNOPSIS
Adds a DNS record to a record set.

## SYNTAX

### A
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv4Address <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### AAAA
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv6Address <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### NS
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Nsdname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### MX
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Exchange <String> -Preference <UInt16>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### PTR
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Ptrdname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### TXT
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Value <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SRV
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Priority <UInt16> -Target <String> -Port <UInt16>
 -Weight <UInt16> [-Profile <AzureProfile>] [<CommonParameters>]
```

### CNAME
```
Add-AzureDnsRecordConfig -RecordSet <DnsRecordSet> -Cname <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureDnsRecordConfig** cmdlet adds a Domain Name System (DNS) record to a **RecordSet** object.
The **RecordSet** object is an offline object, and changes to it do not change the DNS responses until after you run the **Set-AzureDnsRecordSet** cmdlet to persist the change to the Microsoft Azure DNS service.

You cannot remove SOA records.

You can pass the **RecordSet** object to this cmdlet as a parameter or by using the pipeline operator.

## EXAMPLES

### Example 1: Add an A record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -RecordSet $RecordSet -Ipv4Address "172.16.0.0"
```

This command adds an IPv4 address as an A record to the record set stored in the $RecordSet variable.

### Example 2: Add an AAAA record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -RecordSet $RecordSet -Ipv6Address "2001:DB80:4009:1803::1005"
```

This command adds an IPv6 address as an AAAA record to the record set stored in the $RecordSet variable.

### Example 3: Add a CNAME record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -RecordSet $RecordSet -Cname "contoso.com"
```

This command adds contoso.com as a CNAME record to the record set stored in the $RecordSet variable.

### Example 4: Add an MX record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5 -RecordSet $RecordSet
```

This command adds the specified mail exchange server as an MX record to the record set stored in the $RecordSet variable.

### Example 5: Add an NS record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -Nsdname "contoso.myzone.com" -RecordSet $RecordSet
```

This command adds a name server as an NS record to the record set stored in the $RecordSet variable.

### Example 6: Add an SRV record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -Port 8080 -Priority 0 -RecordSet $RecordSet -Target "target.example.com" -Weight 5
```

This command adds the specified service locator as an SRV record to the record set stored in the $RecordSet variable.

### Example 7: Add a TXT record to a record set
```
PS C:\>$RecordSet = Add-AzureDnsRecordConfig -RecordSet $RecordSet -Value "This is a TXT Record"
```

This command adds a TXT record to the record set stored in the $RecordSet variable.

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
Specifies the **RecordSet** object to edit.

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
You can pipe a **RecordSet** object to this cmdlet.
This is an offline representation of the **RecordSet**, and changes to it do not change DNS responses until after you run the **Set-AzureDnsRecordSet** cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
This cmdlet returns the modified **RecordSet** object.

## NOTES

## RELATED LINKS

[Get-AzureDnsRecordSet](.\Get-AzureDnsRecordSet.md)

[Remove-AzureDnsRecordConfig](.\Remove-AzureDnsRecordConfig.md)

[Set-AzureDnsRecordSet](.\Set-AzureDnsRecordSet.md)

