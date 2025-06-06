---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/reset-azhubrouter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Reset-AzHubRouter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Reset-AzHubRouter.md
---

# Reset-AzHubRouter

## SYNOPSIS
Resets the RoutingState of a VirtualHub resource.

## SYNTAX

### ByVirtualHubObject (Default)
```
Reset-AzHubRouter -InputObject <PSVirtualHub> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubName
```
Reset-AzHubRouter -ResourceGroupName <String> -Name <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByVirtualHubResourceId
```
Reset-AzHubRouter -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Resets the Routing State of an existing VirtualHub resource only if the Routing State of the virtual hub is not Provisioned.

## EXAMPLES

### Example 1

```powershell
Reset-AzHubRouter -ResourceGroupName "testRG" -Name "westushub"
```

Reset the routing state of the virtual hub using its ResourceGroupName and ResourceName.

### Example 2

```powershell
Reset-AzHubRouter -ResourceId "/subscriptions/testSub/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub"
```

Reset the routing state of the virtual hub using its ResourceId.

### Example 3

```powershell
Reset-AzHubRouter -InputObject $virtualHub
```

Reset the routing state of the virtual hub using an input object. The input object is of type PSVirtualHub.

### Example 4

```powershell
Get-AzVirtualHub -ResourceGroupName "testRG" -Name "westushub" | Reset-AzHubRouter
```

An existing virtual hub object can be retrieved and then passed as input object to Reset-AzHubRouter.

## PARAMETERS

### -AsJob
Run cmdlet in the background

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
The Virtual hub object to be modified.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualHub
Parameter Sets: ByVirtualHubObject
Aliases: VirtualHub

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The resource name.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases: ResourceName, VirtualHubName, HubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
The resource id of the Virtual hub to be modified.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubResourceId
Aliases: VirtualHubId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

## NOTES

## RELATED LINKS

[Get-AzVirtualHub](./Get-AzVirtualHub.md)
