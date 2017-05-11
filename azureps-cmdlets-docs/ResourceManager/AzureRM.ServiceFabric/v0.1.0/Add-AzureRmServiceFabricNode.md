---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricNode.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/4eb68d2f613c8601986551f21e3e04f476afb8f8
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/b59ab30cc7553989a7f5abf07d2880d6c1e7b21c
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Add-AzureRmServiceFabricNode

## SYNOPSIS
<<<<<<< HEAD
Add nodes to the specific node type in the cluster
=======
Add nodes to the specific node type in the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## SYNTAX

```
Add-AzureRmServiceFabricNode [-ResourceGroupName] <String> [-Name] <String> -NodeType <String> -NumberOfNodesToAdd <Int32>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
User **Add-AzureRmServiceFabricNode** to add nodes to the specific node type. You just need to specify the number of nodes you want to add to a Node Type.
=======
Use **Add-AzureRmServiceFabricNode** to add nodes to the specific node type. You just need to specify the number of nodes you want to add to a node type.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## EXAMPLES

### Example 1
```
PS c:> Add-AzureRmServiceFabricNode -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -NumberOfNodesToAdd 2 -NodeTypeName 'nt1''
```

<<<<<<< HEAD
This command will add 2 nodes to the nodetype 'n1'

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specify the name of the cluster
=======
This command will add 2 nodes to the node type 'n1'.

## PARAMETERS

### -Name
Specify the name of the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeType
<<<<<<< HEAD
Node type name
=======
Node type name.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NumberOfNodesToAdd
<<<<<<< HEAD
VM instance number
=======
VM instance number.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Number

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group.

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

<<<<<<< HEAD
=======
### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
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
<<<<<<< HEAD
[Remove-AzureRmServiceFabricNode](./Remove-AzureRmServiceFabricNode.md)
=======
[Remove-AzureRmServiceFabricNode](./Remove-AzureRmServiceFabricNode.md)
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
