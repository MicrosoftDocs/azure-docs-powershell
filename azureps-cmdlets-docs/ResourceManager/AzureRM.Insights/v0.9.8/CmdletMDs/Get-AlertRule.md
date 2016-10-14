---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Add-AlertRule.md
schema: 2.0.0
---

# Get-AlertRule

## SYNOPSIS
Gets alert rules.

## SYNTAX

### Parameters for GetAlert cmdlet using target resource uri
```
Get-AlertRule -ResourceGroup <String> -TargetResourceId <String> [-DetailedOutput] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Parameters for GetAlert cmdlet
```
Get-AlertRule -ResourceGroup <String> [-DetailedOutput] [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for GetAlert cmdlet using name
```
Get-AlertRule -ResourceGroup <String> -Name <String> [-DetailedOutput] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AlertRule** cmdlet gets alert rules.
Specify the name of a resource group to get the rules for that group, or specify an alert rule by name or URI.

## EXAMPLES

### Example 1: Get alert rules for a resource group
```
PS C:\>Get-AlertRule -ResourceGroup "Default-Web-CentralUS"
```

This command gets all the alert rules for a resource group.

### Example 2: Get an alert rule by using its name
```
PS C:\>Get-AlertRule -ResourceGroup "Default-Web-CentralUS" -Name "contosoalert-7da64548-214d-42ca-b12b-b245bb8f0ac8"
```

This command gets an alert rule identified by name and resource group name.

### Example 3: Get an alert rule by using its name and view details
```
PS C:\>Get-AlertRule -ResourceGroup "Default-Web-CentralUS" -Name "contosoalert-7da64548-214d-42ca-b12b-b245bb8f0ac8" -DetailedOutput
```

This command gets an alert rule identified by name and resource group name.
This command displays details about the alert rules that it gets.

## PARAMETERS

### -ResourceGroup
Specifies the name of the resource group for which this cmdlet gets alert rules.

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
Specifies the name of the alert rule that this cmdlet gets.

```yaml
Type: String
Parameter Sets: Parameters for GetAlert cmdlet using name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DetailedOutput
Indicates that this cmdlet displays detailed information about the objects that it retrieves.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

### -TargetResourceId
Specifies the ID of the target resource for which this cmdlet gets alert rules.

```yaml
Type: String
Parameter Sets: Parameters for GetAlert cmdlet using target resource uri
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

[Add-AlertRule](.\Add-AlertRule.md)

[Get-AlertHistory](.\Get-AlertHistory.md)

[Remove-AlertRule](.\Remove-AlertRule.md)

