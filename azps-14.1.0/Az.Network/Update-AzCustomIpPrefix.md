---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/update-azcustomipprefix
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzCustomIpPrefix.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzCustomIpPrefix.md
---

# Update-AzCustomIpPrefix

## SYNOPSIS
Updates a CustomIpPrefix

## SYNTAX

### UpdateByNameParameterSet (Default)
```
Update-AzCustomIpPrefix -Name <String> -ResourceGroupName <String> [-Commission] [-Decommission] [-Provision]
 [-Deprovision] [-NoInternetAdvertise] [-Cidr <String>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByInputObjectParameterSet
```
Update-AzCustomIpPrefix -InputObject <PSCustomIpPrefix> [-Commission] [-Decommission] [-Provision]
 [-Deprovision] [-NoInternetAdvertise] [-Cidr <String>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByResourceIdParameterSet
```
Update-AzCustomIpPrefix -ResourceId <String> [-Commission] [-Decommission] [-Provision] [-Deprovision]
 [-NoInternetAdvertise] [-Cidr <String>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzCustomIpPrefix** cmdlet allows the user to provision, commission, deprovision or decommission their CustomIpPrefix, or edit the tags or Cidr of the resource.

## EXAMPLES

### Example 1 : Commission the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Commission
```

The above command will start the commissioning process of the CustomIpPrefix.

### Example 2 : Decommission the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Decommission
```

The above command will start the de-commissioning process of the CustomIpPrefix.

### Example 3 : Provision the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Provision
```

The above command will start the provisioning process of the CustomIpPrefix.

### Example 4 : Deprovision the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Deprovision
```

The above command will start the deprovisioning process of the CustomIpPrefix.

### Example 5 : Update tags for the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Tag $tags
```

The above command will update the tags for the CustomIpPrefix.

### Example 6 : Update CIDR for the CustomIpPrefix
```powershell
Update-AzCustomIpPrefix -Name $prefixName -ResourceGroupName $rgName -Cidr $cidr
```

The above command will update the cidr for the CustomIpPrefix. This would work only when resource is in validationfailed state.

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

### -Cidr
The CIDR to update.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Commission
Commission the CustomIpPrefix resource

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

### -Decommission
start decommissioning process.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: Decomission

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

### -Deprovision
Deprovision the CustomIpPrefix resource

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

### -InputObject
The CustomIpPrefix to set.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSCustomIpPrefix
Parameter Sets: UpdateByInputObjectParameterSet
Aliases:

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
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoInternetAdvertise
Commission the CustomIpPrefix resource with no internet advertise

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

### -Provision
Provision the CustomIpPrefix resource

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

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceId
The resource Id.

```yaml
Type: System.String
Parameter Sets: UpdateByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Tag
A hashtable which represents resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateByInputObjectParameterSet, UpdateByResourceIdParameterSet
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

### Microsoft.Azure.Commands.Network.Models.PSCustomIpPrefix

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSCustomIpPrefix

## NOTES

## RELATED LINKS

[Get-AzCustomIpPrefix](./Get-AzCustomIpPrefix.md)

[New-AzCustomIpPrefix](./New-AzCustomIpPrefix.md)

[Remove-AzCustomIpPrefix](./Remove-AzCustomIpPrefix.md)
