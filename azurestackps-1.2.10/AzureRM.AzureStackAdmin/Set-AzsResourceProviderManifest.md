---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Set-AzsResourceProviderManifest

## SYNOPSIS
Updates the provider registration manifest with the new resource provider registration model.

## SYNTAX

```
Set-AzsResourceProviderManifest -ProviderRegistration <ProviderRegistrationModel> -ResourceGroupName <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
The Set-AzsResourceProviderManifest cmdlet updates the provider registration manifest with the new resource provider registration model.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$manifest = Get-AzsResourceProviderManifest -Name "Microsoft.Compute" -ResourceGroupName "system" -Managed; # Modify the manifest object for the need;  Set-AzsResourceProviderManifest -ProviderRegistration $manifest -ResourceGroupName "System"
```

Description

-----------

The example shows how to get the Provider Registration object and then update for the changes.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event. The following values are permitted for this object type.

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies a variable that is used for storing an informational message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Specifies a variable that stores the value of the current pipeline element.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderRegistration
Provider Registration Model object.
Get the object through Get-AzsResourceProviderManifest and modify the values needed.

```yaml
Type: ProviderRegistrationModel
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Resource group name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

