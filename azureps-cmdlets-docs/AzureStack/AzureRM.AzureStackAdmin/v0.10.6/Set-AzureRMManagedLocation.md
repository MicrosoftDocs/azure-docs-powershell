---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMManagedLocation

## SYNOPSIS
Modifies an existing managed location.

## SYNTAX

```
Set-AzureRMManagedLocation -Location <Location> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRMManagedLocation** cmdlet modifies an existing managed location.

## EXAMPLES

### Example 1: Change a property of an existing managed location
```
$locationToUpdate = Get-AzureRMManagedLocation -Name "Chicago"
$locationToUpdate.Longitude = 80.5
Set-AzureRMManagedLocation -Location $locationToUpdate
```

This example modifies the **Longitude** property of the managed location named "Chicago".
The first statement gets the managed location named "Chicago" and stores the object in the $locationToUpdate variable.
After the **Longitude** property is changed, the updated object is passed in the **Location** parameter of the **Set-AzureRMManagedLocation** cmdlet.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

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

### -Location
Specifies an updated **Location** object to be used for updating the existing location data.

```yaml
Type: Location
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.Location

## NOTES

## RELATED LINKS
