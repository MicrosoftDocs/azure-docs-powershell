---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: .\Get-AzureDnsRecordSet.md
schema: 2.0.0
---

# Remove-AzureDnsRecordSet

## SYNOPSIS
Deletes a record set.

## SYNTAX

### Mixed
```
Remove-AzureDnsRecordSet -Name <String> -RecordType <RecordType> -Zone <DnsZone> [-Force] [-PassThru]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Fields
```
Remove-AzureDnsRecordSet -Name <String> -RecordType <RecordType> -ZoneName <String> -ResourceGroupName <String>
 [-Force] [-PassThru] [-Profile <AzureProfile>] [<CommonParameters>]
```

### Object
```
Remove-AzureDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-Force] [-PassThru] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDnsRecordSet** cmdlet deletes the specified record set from the specified zone.
You cannot delete SOA and NS records that are automatically created.

You can pass a **RecordSet** object to this cmdlet by using the pipeline operator or as a parameter.
To identify a record set by name and type without using a **RecordSet** object, you must pass the zone as a **DnsZone** object to this cmdlet by using the pipeline operator or as a parameter, or alternatively you can specify the* ZoneName* parameter.

## EXAMPLES

### Example 1: Remove a record set
```
PS C:\>$RecordSet = Get-AzureDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzureDnsRecordSet -RecordSet $RecordSet
```

The first command gets the specified record set, and then stores it in the $RecordSet variable.

The second command removes the record set in $RecordSet.

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
Specifies the name of the **RecordSet** to remove.

```yaml
Type: String
Parameter Sets: Mixed, Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -RecordSet
Specifies the **RecordSet** to remove.

```yaml
Type: DnsRecordSet
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecordType
Specifies the type of DNS record.
Valid values are: 


- A 
- AAAA 
- CNAME 
- MS 
- NS 
- PTR 
- SRV 
- TXT

You cannot remove record sets for SOA records.

```yaml
Type: RecordType
Parameter Sets: Mixed, Fields
Aliases: 
Accepted values: A, AAAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group that contains the DNS zone that contains the **RecordSet** to delete.

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
Specifies the DNS zone that contains the **RecordSet** to delete.

```yaml
Type: DnsZone
Parameter Sets: Mixed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Specifies the name of the zone that contains the **RecordSet** to delete.

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

### Microsoft.Azure.Commands.Dns.DnsRecordSet
You can pipe a **RecordSet** object to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AzureDnsRecordSet](.\Get-AzureDnsRecordSet.md)

[New-AzureDnsRecordSet](.\New-AzureDnsRecordSet.md)

[Set-AzureDnsRecordSet](.\Set-AzureDnsRecordSet.md)

