---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Set-AzureRmEventHubNamespaceAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Set-AzureRmEventHubNamespaceAuthorizationRule.md
gitcommit: https://github.com/Azure/azure-powershell/blob/28baa4a53a4efceb1197c032a8db08e199f0858d
---

# Set-AzureRmEventHubNamespaceAuthorizationRule

## SYNOPSIS
Updates the authorization rule on the specified Event Hubs namespace.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmEventHubNamespaceAuthorizationRule [-ResourceGroupName] <String> [-NamespaceName] <String>
 [-AuthRuleObj] <AuthorizationRuleAttributes> [[-AuthorizationRuleName] <String>] [-Rights <String[]>]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Set-AzureRmEventHubNamespaceAuthorizationRule cmdlet updates the authorization rule on the specified Event Hubs namespace.

## EXAMPLES

### Example 1
```
PS C:\> Set-AzureRmEventHubNamespaceAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -AuthorizationRuleName MyAuthRuleName -Rights @("Manage")
```

Updates the authorization rule \`MyAuthRuleName\` to grant Manage rights.

## PARAMETERS

### -AuthorizationRuleName
The authorization rule name.
Required if -AuthruleObj is not specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthRuleObj
The Event Hubs namespace authorization rule object.

```yaml
Type: AuthorizationRuleAttributes
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NamespaceName
The Event Hubs namespace name.

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
Resource group name.

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

### -Rights
Required if -AuthruleObj is not specified.
Rights; for example,  @("Listen","Send","Manage")

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.SharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS

