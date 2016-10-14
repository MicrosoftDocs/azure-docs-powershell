---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Add-AlertRule.md
schema: 2.0.0
---

# Remove-AlertRule

## SYNOPSIS
Removes an alert rule.

## SYNTAX

```
Remove-AlertRule -ResourceGroup <String> -Name <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AlertRule** cmdlet removes an alert rule.
Specify the rule name and resource group name of the rule to remove.

## EXAMPLES

### Example 1: Remove an alert rule
```
PS C:\>Remove-AlertRule -ResourceGroup "Default-Web-CentralUS" -Name "alert-7da64548-214d-42ca-b12b-b245bb8f0ac8"
RequestId                                                            StatusCode
---------                                                            ----------
2c6c159b-0e73-4a01-a67b-c32c1a0008a3                                         OK
```

This command removes the alert rule that has the specified name and resource group name.

## PARAMETERS

### -ResourceGroup
Specifies name of the resource group that includes the alert rule that this cmdlet removes.

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

### -Name
Specifies the name of the alert rule that this cmdlet removes.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AlertRule](.\Add-AlertRule.md)

[Get-AlertRule](.\Get-AlertRule.md)

[Get-AlertHistory](.\Get-AlertHistory.md)

