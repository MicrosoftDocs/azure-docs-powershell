---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmEventHubNamespace

## SYNOPSIS
Removes the specified Event Hubs namespace.

## SYNTAX

```
Remove-AzureRmEventHubNamespace [-ResourceGroupName] <String> [-NamespaceName] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmEventHubNamespace** cmdlet removes and deletes the specified Event Hubs namespace.

## EXAMPLES

### Example 1: Remove the specified Event Hub namespace
```
PS C:\> Remove-AzureRmEventHubNamespace -ResourceGroupName "MyResourceGroupName" -NamespaceName "MyNamespaceName"
```

This command removes the Event Hubs namespace named MyNamespaceName that is contained in the resource group named MyResourceGroupName.

## PARAMETERS

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

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureRmEventHubNamespace](./Get-AzureRmEventHubNamespace.md)

[New-AzureRmEventHubNamespace](./New-AzureRmEventHubNamespace.md)

[Set-AzureRmEventHubNamespace](./Set-AzureRmEventHubNamespace.md)
