---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Remove-AzureRmServiceFabricSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Remove-AzureRmServiceFabricSetting.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/5d5311bad38bc57d0768a327dcbfba8bfc400794
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/928c918a88f76273c14645e599fb59baea0cb3d6
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Remove-AzureRmServiceFabricSetting

## SYNOPSIS
<<<<<<< HEAD
Remove one or multiple ServiceFabric setting from the cluster
=======
Remove one or multiple Service Fabric setting from the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## SYNTAX

### OneSetting
```
Remove-AzureRmServiceFabricSetting [-ResourceGroupName] <String> [-Name] <String> -Section <String>
 -Parameter <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BatchSettings
```
Remove-AzureRmServiceFabricSetting [-ResourceGroupName] <String> [-Name] <String>
 -SettingsSectionDescription <PSSettingsSectionDescription[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
Use **Remove-AzureRmServiceFabricSetting** to remove Service Fabric settings from the cluster
=======
Use **Remove-AzureRmServiceFabricSetting** to remove Service Fabric settings from the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## EXAMPLES

### Example 1
```
PS c:> Remove-AzureRmServiceFabricSetting -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -Section 'EseStore' -Parameter 'MaxCursors'
```

<<<<<<< HEAD
This command will remove settings 'MaxCursors' under 'EseStore' section

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
This command will remove settings 'MaxCursors' under 'EseStore' section.

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

### -Parameter
<<<<<<< HEAD
Parameter
=======
Parameter.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: OneSetting
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

### -Section
<<<<<<< HEAD
Section
=======
Section.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: OneSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SettingsSectionDescription
<<<<<<< HEAD
Client authentication type
=======
Client authentication type.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: PSSettingsSectionDescription[]
Parameter Sets: BatchSettings
Aliases: 

Required: True
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

### System.String
Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsSectionDescription[]

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PsCluster

## NOTES

## RELATED LINKS

