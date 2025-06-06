---
external help file: Az.FluidRelay-help.xml
Module Name: Az.FluidRelay
online version: https://learn.microsoft.com/powershell/module/az.fluidrelay/get-azfluidrelayserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FluidRelay/FluidRelay/help/Get-AzFluidRelayServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FluidRelay/FluidRelay/help/Get-AzFluidRelayServer.md
---

# Get-AzFluidRelayServer

## SYNOPSIS
Get a Fluid Relay server.

## SYNTAX

### List (Default)
```
Get-AzFluidRelayServer [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentityResourceGroup
```
Get-AzFluidRelayServer -Name <String> -ResourceGroupInputObject <IFluidRelayIdentity>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get
```
Get-AzFluidRelayServer -Name <String> -ResourceGroup <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### List1
```
Get-AzFluidRelayServer -ResourceGroup <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzFluidRelayServer -InputObject <IFluidRelayIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Get a Fluid Relay server.

## EXAMPLES

### Example 1: List Fluid Relay server.
```powershell
Get-AzFluidRelayServer
```

```output
Location Name            ResourceGroupName
-------- ----            -----------------
westus2  azps-fluidrelay azpstest-gp
```

List Fluid Relay server.

### Example 2: List Fluid Relay server by ResourceGroup.
```powershell
Get-AzFluidRelayServer -ResourceGroup azpstest-gp
```

```output
Location Name            ResourceGroupName
-------- ----            -----------------
westus2  azps-fluidrelay azpstest-gp
```

List Fluid Relay server.

### Example 3: Get a Fluid Relay server by ResourceGroup.
```powershell
Get-AzFluidRelayServer -Name azps-fluidrelay -ResourceGroup azpstest-gp
```

```output
Location Name            ResourceGroupName
-------- ----            -----------------
westus2  azps-fluidrelay azpstest-gp
```

Get a Fluid Relay server.

## PARAMETERS

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.FluidRelay.Models.IFluidRelayIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The Fluid Relay server resource name.

```yaml
Type: System.String
Parameter Sets: GetViaIdentityResourceGroup, Get
Aliases: FluidRelayServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroup
The resource group containing the resource.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupInputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.FluidRelay.Models.IFluidRelayIdentity
Parameter Sets: GetViaIdentityResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionId
The subscription id (GUID) for this resource.

```yaml
Type: System.String[]
Parameter Sets: List, Get, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.FluidRelay.Models.IFluidRelayIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.FluidRelay.Models.IFluidRelayServer

## NOTES

## RELATED LINKS
