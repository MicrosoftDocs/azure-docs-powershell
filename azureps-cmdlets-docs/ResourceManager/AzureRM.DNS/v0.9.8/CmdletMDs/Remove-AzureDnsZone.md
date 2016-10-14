---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
online version: .\Get-AzureDnsZone.md
schema: 2.0.0
---

# Remove-AzureDnsZone

## SYNOPSIS
Removes a DNS zone from a resource group.

## SYNTAX

### Fields
```
Remove-AzureDnsZone -Name <String> -ResourceGroupName <String> [-Force] [-PassThru] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Object
```
Remove-AzureDnsZone -Zone <DnsZone> [-Overwrite] [-Force] [-PassThru] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDnsZone** cmdlet removes a Domain Name System (DNS) zone from a specified resource group.
Before you run this cmdlet, you must first remove all record sets from the zone that you want to remove.

You can pass a **DnsZone** object to this cmdlet as a parameter or by using the pipeline operator, or alternatively you can specify its name.

## EXAMPLES

### Example 1: Remove a zone
```
PS C:\>Remove-AzureDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

This command removes the zone named myzone.com from the resource group named MyResourceGroup.

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
Specifies the name of the DNS zone to remove.

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
Indicates that this cmdlet ignores the Etag when deleting the resource group, and that the resource group is removed even if it has changed since the last Get.

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
@{Text=}

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
Specifies the name of the resource group that contains the zone to remove.

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
Specifies the DNS zone to remove.

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

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AzureDnsZone](.\Get-AzureDnsZone.md)

[New-AzureDnsZone](.\New-AzureDnsZone.md)

[Set-AzureDnsZone](.\Set-AzureDnsZone.md)

