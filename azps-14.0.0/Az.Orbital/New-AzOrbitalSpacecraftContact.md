---
external help file: Az.Orbital-help.xml
Module Name: Az.Orbital
online version: https://learn.microsoft.com/powershell/module/az.orbital/new-azorbitalspacecraftcontact
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Orbital/Orbital/help/New-AzOrbitalSpacecraftContact.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Orbital/Orbital/help/New-AzOrbitalSpacecraftContact.md
---

# New-AzOrbitalSpacecraftContact

## SYNOPSIS
create a contact.

## SYNTAX

### CreateExpanded (Default)
```
New-AzOrbitalSpacecraftContact -Name <String> -ResourceGroupName <String> -SpacecraftName <String>
 [-SubscriptionId <String>] -ContactProfileId <String> -GroundStationName <String>
 -ReservationEndTime <DateTime> -ReservationStartTime <DateTime> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateViaJsonString
```
New-AzOrbitalSpacecraftContact -Name <String> -ResourceGroupName <String> -SpacecraftName <String>
 [-SubscriptionId <String>] -JsonString <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateViaJsonFilePath
```
New-AzOrbitalSpacecraftContact -Name <String> -ResourceGroupName <String> -SpacecraftName <String>
 [-SubscriptionId <String>] -JsonFilePath <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateViaIdentitySpacecraftExpanded
```
New-AzOrbitalSpacecraftContact -Name <String> -SpacecraftInputObject <IOrbitalIdentity>
 -ContactProfileId <String> -GroundStationName <String> -ReservationEndTime <DateTime>
 -ReservationStartTime <DateTime> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
create a contact.

## EXAMPLES

### Example 1: Creates a contact.
```powershell
$dateS = Get-Date -Year 2023 -Month 5 -Day 10 -Hour 11 -Minute 06 -Second 07
$dateE = Get-Date -Year 2023 -Month 5 -Day 10 -Hour 11 -Minute 16 -Second 21

New-AzOrbitalSpacecraftContact -Name azps-orbital-contact -ResourceGroupName azpstest-gp -SpacecraftName SwedenAQUASpacecraft -ContactProfileId "/subscriptions/11111111-2222-3333-4444-123456789101/resourceGroups/azpstest-gp/providers/Microsoft.Orbital/contactProfiles/Sweden-contactprofile" -GroundStationName "Microsoft_Gavle" -ReservationStartTime $dateS -ReservationEndTime $dateE
```

```output
Name                 GroundStationName Status    ReservationStartTime ReservationEndTime   ResourceGroupName
----                 ----------------- ------    -------------------- ------------------   -----------------
azps-orbital-contact Microsoft_Gavle   scheduled 5/10/2023 3:06:07 AM 5/10/2023 3:16:21 AM azpstest-gp
```

Creates a contact.

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

### -ContactProfileId
Resource ID.

```yaml
Type: System.String
Parameter Sets: CreateExpanded, CreateViaIdentitySpacecraftExpanded
Aliases:

Required: True
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

### -GroundStationName
Azure Ground Station name.

```yaml
Type: System.String
Parameter Sets: CreateExpanded, CreateViaIdentitySpacecraftExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Create operation

```yaml
Type: System.String
Parameter Sets: CreateViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Create operation

```yaml
Type: System.String
Parameter Sets: CreateViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Contact name.

```yaml
Type: System.String
Parameter Sets: (All)
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

### -ReservationEndTime
Reservation end time of a contact (ISO 8601 UTC standard).

```yaml
Type: System.DateTime
Parameter Sets: CreateExpanded, CreateViaIdentitySpacecraftExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReservationStartTime
Reservation start time of a contact (ISO 8601 UTC standard).

```yaml
Type: System.DateTime
Parameter Sets: CreateExpanded, CreateViaIdentitySpacecraftExpanded
Aliases:

Required: True
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
Parameter Sets: CreateExpanded, CreateViaJsonString, CreateViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpacecraftInputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Orbital.Models.IOrbitalIdentity
Parameter Sets: CreateViaIdentitySpacecraftExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SpacecraftName
Spacecraft ID.

```yaml
Type: System.String
Parameter Sets: CreateExpanded, CreateViaJsonString, CreateViaJsonFilePath
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
Parameter Sets: CreateExpanded, CreateViaJsonString, CreateViaJsonFilePath
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

### Microsoft.Azure.PowerShell.Cmdlets.Orbital.Models.IOrbitalIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Orbital.Models.IContact

## NOTES

## RELATED LINKS
