---
external help file: 
Module Name: Az.VoiceServices
online version: https://learn.microsoft.com/powershell/module/az.voiceservices/remove-azvoiceservicescommunicationscontact
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VoiceServices/help/Remove-AzVoiceServicesCommunicationsContact.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VoiceServices/help/Remove-AzVoiceServicesCommunicationsContact.md
---

# Remove-AzVoiceServicesCommunicationsContact

## SYNOPSIS
Delete a Contact

## SYNTAX

### Delete (Default)
```
Remove-AzVoiceServicesCommunicationsContact -CommunicationsGatewayName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzVoiceServicesCommunicationsContact -InputObject <IVoiceServicesIdentity> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Delete a Contact

## EXAMPLES

### Example 1: Delete a contact
```powershell
Remove-AzVoiceServicesCommunicationsContact -ResourceGroupName vtest-communication-rg -CommunicationsGatewayName vsc-gateway-pwsh01 -Name gateway-01
```

Delete a contact.

### Example 2: Delete a contact by pipeline
```powershell
Get-AzVoiceServicesCommunicationsContact -ResourceGroupName vtest-communication-rg -CommunicationsGatewayName vsc-gateway-pwsh01 -Name gateway-01 | Remove-AzVoiceServicesCommunicationsContact
```

Delete a contact by pipeline.

## PARAMETERS

### -AsJob
Run the command as a job

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

### -CommunicationsGatewayName
Unique identifier for this deployment

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

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
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VoiceServices.Models.IVoiceServicesIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Unique identifier for this contact

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: ContactName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

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

### -PassThru
Returns true when the command succeeds

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
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.VoiceServices.Models.IVoiceServicesIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


`INPUTOBJECT <IVoiceServicesIdentity>`: Identity Parameter
  - `[CommunicationsGatewayName <String>]`: Unique identifier for this deployment
  - `[ContactName <String>]`: Unique identifier for this contact
  - `[Id <String>]`: Resource identity path
  - `[ResourceGroupName <String>]`: The name of the resource group. The name is case insensitive.
  - `[SubscriptionId <String>]`: The ID of the target subscription.
  - `[TestLineName <String>]`: Unique identifier for this test line

## RELATED LINKS
