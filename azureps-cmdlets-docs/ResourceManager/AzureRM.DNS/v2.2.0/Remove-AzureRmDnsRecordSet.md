---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 286CC92A-036E-4ECE-AA6B-1B385A8DDA75
---

# Remove-AzureRmDnsRecordSet

## SYNOPSIS
Deletes a record set.

## SYNTAX

### Fields
```
Remove-AzureRmDnsRecordSet -Name <String> -RecordType <RecordType> -ZoneName <String>
 -ResourceGroupName <String> [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Mixed
```
Remove-AzureRmDnsRecordSet -Name <String> -RecordType <RecordType> -Zone <DnsZone> [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-AzureRmDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-Force] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmDnsRecordSet** cmdlet deletes the specified record set from the specified zone.
You cannot delete SOA or name server (NS) records that are automatically created at the zone apex.

You can pass a **RecordSet** object to this cmdlet by using the pipeline operator or as a parameter.
To identify a record set by name and type without using a **RecordSet** object, you must pass the zone as a **DnsZone** object to this cmdlet by using the pipeline operator or as a parameter, or alternatively you can specify the *ZoneName* and *ResourceGroupName* parameters.

The *Confirm* parameter and $ConfirmPreference pn_PowerShell_short variable can be used to control the standard pn_PowerShell_short confirmation behavior.

Because of the potential impact of deleting an in-use zone, a second level of confirmation is used in addition to the standard pn_PowerShell_short behavior.
This can be suppressed using the *Force* parameter.

When specifying the record set using a **RecordSet** object, the record set is not deleted if it has been changed in Azure DNS since the local **RecordSet** object was retrieved.
This provides protection for concurrent changes.
You can suppress this by using the *Overwrite* parameter, which deletes the record set regardless of concurrent changes.

## EXAMPLES

### Example 1: Remove a record set
```
PS C:\> $RecordSet = Get-AzureRmDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzureRmDnsRecordSet -RecordSet $RecordSet
```

The first command gets the specified record set, and then stores it in the $RecordSet variable.The second command removes the record set in $RecordSet.

### Example 2: Remove a record set and suppress all confirmation
```
PS C:\> $RecordSet = Get-AzureRmDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" 
PS C:\> Remove-AzureRmDnsRecordSet -RecordSet $RecordSet -Confirm:$False -Force -Overwrite 

# Alternatively, the record set can be removed as follows.  In this case, 
# because the record set is specified by name rather than by object, the 
# Overwrite parameter is not applicable.

PS C:\> Remove-AzureRmDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Confirm:$False -Force
```

The first command gets the specified record set.

The second command deletes the record set, even if it has changed in the meantime.
Confirmation prompts are suppressed.

## PARAMETERS

### -Force
ps_force

This confirmation is in addition to the standard pn_PowerShell_short confirmation controlled via the *Confirm* parameter and $ConfirmPreference pn_PowerShell_short variable.

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
When specifying the record set by name, the DNS zone must be specified using either the *Zone* parameter or the *ZoneName* and *ResourceGroupName* parameters.

Alternatively, the record set can be specified using a **RecordSet** object, passed using the *RecordSet* parameter.

```yaml
Type: String
Parameter Sets: Fields, Mixed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overwrite
When specifying the record set using a **RecordSet** object, the record set is not deleted if it has been changed in Azure DNS since the local **RecordSet** object was retrieved.
This provides protection for concurrent changes.
This can be suppressed using the *Overwrite* parameter, which deletes the record set regardless of concurrent changes.

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
passthru

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

### -RecordSet
Specifies the **RecordSet** object to remove.

Alternatively, the record set can be specified using the *Name* and *Zone* parameters, or using the *Name*, *ZoneName*, and *ResourceGroupName* parameters.

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
- MX
- NS
- PTR
- SRV 
- TXT

SOA records are deleted automatically when the zone is deleted.
You cannot manually delete SOA records.

```yaml
Type: RecordType
Parameter Sets: Fields, Mixed
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
This parameter is applicable only when the record set and DNS zone are specified using the *Name* and *ZoneName* parameters.

Alternatively, you can specify the record set using either the *RecordSet* parameter, or the *Name* and *Zone* parameters.

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
This parameter is applicable only when specifying the record set using the *Name* parameter.

Alternatively, you can specify the record set using either the *RecordSet* parameter, or the *Name*, *ZoneName*, and *ResourceGroupName* parameters.

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
You must also specify the *Name* and *ResourceGroupName* parameters.

Alternatively, the record set can be specified using either the *RecordSet* parameter, or the *Name* and *Zone* parameters.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Get-AzureRmDnsRecordSet](./Get-AzureRmDnsRecordSet.md)

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Set-AzureRmDnsRecordSet](./Set-AzureRmDnsRecordSet.md)


