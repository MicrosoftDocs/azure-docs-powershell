---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzsGalleryItem

## SYNOPSIS
Gets the details of an existing gallery item.

## SYNTAX

```
Get-AzsGalleryItem [-Name <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The Get-AzsGalleryItem cmdlet gets details of an existing gallery item.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-AzsGalleryItem -Name "Microsoft.SqlDatabase.0.1.0"
```

Description

-----------

The example gets the gallery item named 'Microsoft.SqlDatabase.0.1.0'

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
Specifies the gallery item name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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


