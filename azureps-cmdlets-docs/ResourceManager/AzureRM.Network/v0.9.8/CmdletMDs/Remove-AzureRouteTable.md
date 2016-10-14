---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureRouteTable.md
schema: 2.0.0
---

# Remove-AzureRouteTable

## SYNOPSIS
Removes a route table.

## SYNTAX

```
Remove-AzureRouteTable -Name <String> -ResourceGroupName <String> [-Force] [-PassThru]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRouteTable** cmdlet removes an Azure route table.

## EXAMPLES

### Example 1: Remove a route table
```
PS C:\>Remove-AzureRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01"
Confirm
Are you sure you want to remove resource 'routetable01'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the route table named routetable01 in the resource group named ResourceGroup11.
The cmdlet prompts you for confirmation before it removes the table.

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
Specifies the name of the route table that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a value of $True if it removes a route table, or $False if it fails.
If you do not specify this parameter, this cmdlet returns no value.

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
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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
Specifies the name of the resource group that contains the route table that this cmdlet removes.```yaml
Type: String
Parameter Sets: (All)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRouteTable](.\Get-AzureRouteTable.md)

[New-AzureRouteTable](.\New-AzureRouteTable.md)

[Set-AzureRouteTable](.\Set-AzureRouteTable.md)

