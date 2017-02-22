---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmEventHubNamespaceAuthorizationRule

## SYNOPSIS
Gets the details of an Event Hubs namespace authorization rule, or gets a list of authorization rules.

## SYNTAX

```
Get-AzureRmEventHubNamespaceAuthorizationRule [-ResourceGroupName] <String> [-NamespaceName] <String>
 [[-AuthorizationRuleName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmEventHubNamespaceAuthorizationRule** cmdlet gets either the details of a specified Event Hubs namespace authorization rule, or a list of namespace authorization rules. If the authorization rule name is provided, the details of a single authorization rule is returned. If an authorization rule name is not provided, a list of all authorization rules in the namespace is returned.

## EXAMPLES

### Example 1: Get a specific namespace authorization rule
```
PS C:\> Get-AzureRmEventHubNamespaceAuthorizationRule -ResourceGroupName "MyResourceGroupName" -NamespaceName "MyNamespaceName" -AuthorizationRuleName "MyAuthRuleName"
```

This command gets the authorization rule named MyAuthRuleName in the Event Hubs namespace named MyNamespaceName that belongs to the resource group named MyResourceGroupName.

### Example 2: Get the default namespace authorization rule
```
PS C:\> Get-AzureRmEventHubNamespaceAuthorizationRule -ResourceGroupName "MyResourceGroupName" -NamespaceName "MyNamespaceName" -AuthorizationRuleName "RootManageSharedAccessKey"
```

This command gets the default authorization rule named RootManageSharedAccessKey in the Event Hubs namespace named MyNamespaceName that belongs to the resource group named MyResourceGroupName.

### Example 3: Get all namespace authorization rules
```
PS C:\> Get-AzureRmEventHubNamespaceAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName
```

This command gets all authorization rules in the Event Hubs namespace named MyNamespaceName that belongs to the resource group named MyResourceGroupName.

## PARAMETERS

### -AuthorizationRuleName
Specifies the name of the Event Hubs namespace authorization rule that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NamespaceName
Specifies the name of the namespace.


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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.EventHub.Models.SharedAccessAuthorizationRuleAttributes, Microsoft.Azure.Commands.EventHub, Version=0.0.1.0, Culture=neutral, PublicKeyToken=null]]

## NOTES

## RELATED LINKS

[New-AzureRmEventHubNamespaceAuthorizationRule](./New-AzureRmEventHubNamespaceAuthorizationRule.md)

[Remove-AzureRmEventHubNamespaceAuthorizationRule](./Remove-AzureRmEventHubNamespaceAuthorizationRule.md)

[Set-AzureRmEventHubNamespaceAuthorizationRule](./Set-AzureRmEventHubNamespaceAuthorizationRule.md)
