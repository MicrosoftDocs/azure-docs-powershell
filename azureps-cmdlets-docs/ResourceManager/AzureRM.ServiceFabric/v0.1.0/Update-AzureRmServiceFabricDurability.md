---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Update-AzureRmServiceFabricDurability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Update-AzureRmServiceFabricDurability.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/68c7c4760351d141341278ae635b16ec8c502b9b
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/928c918a88f76273c14645e599fb59baea0cb3d6
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Update-AzureRmServiceFabricDurability

## SYNOPSIS
<<<<<<< HEAD
Update the durability tier or VmSku of a nodetype in the cluster.
=======
Update the durability tier or VmSku of a node type in the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## SYNTAX

```
Update-AzureRmServiceFabricDurability [-ResourceGroupName] <String> [-Name] <String> -NodeType <String>
 -DurabilityLevel <DurabilityLevel> [-Sku <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
Use **Update-AzureRmServiceFabricDurability** to update durability or SKU of the cluter 
=======
Use **Update-AzureRmServiceFabricDurability** to update durability or SKU of the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## EXAMPLES

### Example 1
```
PS c:> Update-AzureRmServiceFabricDurability -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -DurabilityLevel Silver -NodeType nt1
```

<<<<<<< HEAD
This command changes durability tier of the nodetype 'nt1' to silver.

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

### -DurabilityLevel
Specify durability Level
=======
This command changes durability tier of the NodeType 'nt1' to silver.

## PARAMETERS

### -DurabilityLevel
Specify durability level.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: DurabilityLevel
Parameter Sets: (All)
Aliases: Level
Accepted values: Bronze, Silver, Gold

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
<<<<<<< HEAD
Specify the name of the cluster
=======
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
Specify Service Fabric node type name
=======
Specify Service Fabric node type name.
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

### -Sku
<<<<<<< HEAD
Specify the SKU of the node type
=======
Specify the SKU of the node type.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.ServiceFabric.Models.DurabilityLevel
System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PsCluster

## NOTES

## RELATED LINKS

