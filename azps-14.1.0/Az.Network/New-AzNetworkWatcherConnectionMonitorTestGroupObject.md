---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/new-aznetworkwatcherconnectionmonitortestgroupobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorTestGroupObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorTestGroupObject.md
---

# New-AzNetworkWatcherConnectionMonitorTestGroupObject

## SYNOPSIS
Create a connection monitor test group.

## SYNTAX

```
New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name <String>
 -TestConfiguration <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorTestConfigurationObject]>
 -Source <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorEndpointObject]>
 -Destination <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorEndpointObject]>
 [-Disable] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The New-AzNetworkWatcherConnectionMonitorTestGroupObject cmdlet creates a connection monitor test group.

## EXAMPLES

### Example 1: Create a test group with 2 testConfigurations, w source and 2 destination endpoints

```powershell
$testGroup1 = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name testGroup1 -TestConfiguration $tcpTestConfiguration, $icmpTestConfiguration -Source $vmEndpoint, $workspaceEndpoint -Destination $bingEndpoint, $googleEndpoint
```

## PARAMETERS

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

### -Destination
List of destination endpoints.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorEndpointObject]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Flag indicating whether test group is disabled.

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

### -Name
The test group name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
List of source endpoints.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorEndpointObject]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestConfiguration
List of test configuration.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorTestConfigurationObject]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### None

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorTestGroupObject

## NOTES

## RELATED LINKS
