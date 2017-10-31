---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzsResourceProviderManifest

## SYNOPSIS
Gets the resource provider manifest registration details.

## SYNTAX

```
Get-AzsResourceProviderManifest [-Name <String>] -ResourceGroupName <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The Get-AzsResourceProviderManifest cmdlet gets the resource provider manifest registration details.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$registration = Get-AzsResourceProviderManifest -Name "Microsoft.Sql.Admin" -ResourceGroupName System
```

Description

-----------

The following example gets the registration manifest details for the Microsoft.Sql.Admin namespace

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

### -Name
Specifies the name of the resource provider manifest.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

### -ResourceGroupName
Resource group name

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


