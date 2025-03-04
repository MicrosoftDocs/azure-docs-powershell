---
external help file: Az.DevCenter-help.xml
Module Name: Az.DevCenter
online version: https://learn.microsoft.com/powershell/module/az.devcenter/start-azdevcenteruserdevbox
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevCenter/DevCenter/help/Start-AzDevCenterUserDevBox.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevCenter/DevCenter/help/Start-AzDevCenterUserDevBox.md
---

# Start-AzDevCenterUserDevBox

## SYNOPSIS
Starts a Dev Box

## SYNTAX

### Start (Default)
```
Start-AzDevCenterUserDevBox -Endpoint <String> -Name <String> -ProjectName <String> [-UserId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StartViaIdentity
```
Start-AzDevCenterUserDevBox -Endpoint <String> -InputObject <IDevCenterdataIdentity>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StartViaIdentityByDevCenter
```
Start-AzDevCenterUserDevBox -DevCenterName <String> -InputObject <IDevCenterdataIdentity>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StartByDevCenter
```
Start-AzDevCenterUserDevBox -DevCenterName <String> -Name <String> -ProjectName <String> [-UserId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Starts a Dev Box

## EXAMPLES

### Example 1: Start a dev box by endpoint
```powershell
Start-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -ProjectName DevProject -UserId 00aa00aa-bb11-cc22-dd33-44ee44ee44ee -Name myDevBox
```

This command starts the dev box "myDevBox" assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

### Example 2: Start a dev box by dev center
```powershell
Start-AzDevCenterUserDevBox -DevCenterName Contoso -ProjectName DevProject -UserId "me" -Name myDevBox
```

This command starts the dev box "myDevBox" assigned to the currently signed-in user.

### Example 3: Start a dev box by endpoint and InputObject
```powershell
$devBoxInput = @{"DevBoxName" = "myDevBox"; "UserId" = "me"; "ProjectName" = "DevProject" }
Start-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -InputObject $devBoxInput
```

This command starts the dev box "myDevBox" assigned to the currently signed-in user.

### Example 4: Start a dev box by dev center and InputObject
```powershell
$devBoxInput = @{"DevBoxName" = "myDevBox"; "UserId" = "00aa00aa-bb11-cc22-dd33-44ee44ee44ee"; "ProjectName" = "DevProject" }
Start-AzDevCenterUserDevBox -DevCenterName Contoso -InputObject $devBoxInput
```

This command starts the dev box "myDevBox" assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

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

### -DevCenterName
The DevCenter upon which to execute operations.

```yaml
Type: System.String
Parameter Sets: StartViaIdentityByDevCenter, StartByDevCenter
Aliases: DevCenter

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint
The DevCenter-specific URI to operate on.

```yaml
Type: System.String
Parameter Sets: Start, StartViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DevCenterdata.Models.IDevCenterdataIdentity
Parameter Sets: StartViaIdentity, StartViaIdentityByDevCenter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The name of a Dev Box.

```yaml
Type: System.String
Parameter Sets: Start, StartByDevCenter
Aliases: DevBoxName

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

### -ProjectName
The DevCenter Project upon which to execute operations.

```yaml
Type: System.String
Parameter Sets: Start, StartByDevCenter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserId
The AAD object id of the user.
If value is 'me', the identity is taken from the authentication context.

```yaml
Type: System.String
Parameter Sets: Start, StartByDevCenter
Aliases:

Required: False
Position: Named
Default value: "me"
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

### Microsoft.Azure.PowerShell.Cmdlets.DevCenterdata.Models.IDevCenterdataIdentity

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
