---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: http://azure.microsoft.com/en-us/documentation/articles/azure-preview-portal-using-tags/
schema: 2.0.0
---

# New-AzureDnsRecordSet

## SYNOPSIS
Creates a DNS record set.

## SYNTAX

### Fields
```
New-AzureDnsRecordSet -Name <String> -ZoneName <String> -ResourceGroupName <String> -Ttl <UInt32>
 -RecordType <RecordType> [-Tag <Hashtable[]>] [-Overwrite] [-Force] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Object
```
New-AzureDnsRecordSet -Name <String> -Zone <DnsZone> -Ttl <UInt32> -RecordType <RecordType>
 [-Tag <Hashtable[]>] [-Overwrite] [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureDnsRecordSet** cmdlet creates a new Domain Name System (DNS) record set with the specified name and type in the specified zone.
A **RecordSet** is a set of DNS records with the same name and type.
Note that the name is relative to the zone and not the fully qualified name.

You can use the pipeline operator to pass a **DnsZone** object to this cmdlet, or you can pass a **DnsZone** object as the *Zone* parameter, or alternatively you can specify the zone by name.

If a matching **RecordSet** already exists, you must specify the *Overwrite* parameter, otherwise the cmdlet will not create a new **RecordSet**.

## EXAMPLES

### Example 1: Create a RecordSet
```
PS C:\>$RecordSet = New-AzureDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com"
```

This command creates a new **RecordSet** named www as type A in the zone named myzone.com with a TTL of 3600 seconds.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.
You can use the *Force* parameter with the *Overwrite* parameter to overwrite an existing **RecordSet**.

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
Specifies the name of the **RecordSet** to create.

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

### -Overwrite
Indicates that this cmdlet overwrites the specified **RecordSet** if it exists.
You will be prompted to confirm the operation unless you specify the *Force* parameter.

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
Specifies the type of DNS record to create.
Valid values are: 


- A 
- AAAA
- CNAME
- MS
- NS
- PTR
- SRV 
- TXT

SOA records are created automatically when the zone is created and cannot be created manually.

```yaml
Type: RecordType
Parameter Sets: (All)
Aliases: 
Accepted values: A, AAAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group that contains the zone.

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
Specifies an array of tags to associate with the **RecordSet**.
Tags are name-value pairs that are represented as hash tables, for example @(@{"Name"="dept"; "Value"="shopping"}, @{"Name"="env"; "Value"="production"}).

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ttl
Specifies the Time to Live (TTL).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Specifies the **DnsZone** in which to create the **RecordSet**.

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
Specifies the name of the zone in which to create the **RecordSet**.

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

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
This cmdlet returns a **RecordSet** object.

## NOTES

## RELATED LINKS

[Using tags to organize your Azure resources](http://azure.microsoft.com/en-us/documentation/articles/azure-preview-portal-using-tags/)

[Get-AzureDnsRecordSet](.\Get-AzureDnsRecordSet.md)

[Remove-AzureDnsRecordSet](.\Remove-AzureDnsRecordSet.md)

[Set-AzureDnsRecordSet](.\Set-AzureDnsRecordSet.md)

