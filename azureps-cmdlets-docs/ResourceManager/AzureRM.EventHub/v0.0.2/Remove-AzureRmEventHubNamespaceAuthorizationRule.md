---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmEventHubNamespaceAuthorizationRule

## SYNOPSIS
Removes the specified authorization rule on the given Event Hubs namespace.

## SYNTAX

```
Remove-AzureRmEventHubNamespaceAuthorizationRule [-ResourceGroupName] <String> [-NamespaceName] <String>
 [-AuthorizationRuleName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmEventHubNamespaceAuthorizationRule** cmdlet removes and deletes the specified authorization rule on the given Event Hubs namespace.

## EXAMPLES

### Example 1
```
PS C:\> Remove-AzureRmEventHubNamespaceAuthorizationRule -ResourceGroupName "MyResourceGroupName" -NamespaceName "MyNamespaceName" -AuthorizationRuleName "AuthRule001"
```

This command removes the authorization rule named AuthRule001 from the namespace named MyNamespaceName.

## PARAMETERS

### -AuthorizationRuleName
Specifies the name of the Event Hub namespace authorization rule that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -NamespaceName
Specifies the name of the Event Hubs namespace.


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the Event Hub.


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzureRmEventHubNamespaceAuthorizationRule](./Get-AzureRmEventHubNamespaceAuthorizationRule.md)

[New-AzureRmEventHubNamespaceAuthorizationRule](./New-AzureRmEventHubNamespaceAuthorizationRule.md)

[Set-AzureRmEventHubNamespaceAuthorizationRule](./Set-AzureRmEventHubNamespaceAuthorizationRule.md)
