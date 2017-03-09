---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 7690143F-5F09-4739-9F66-B2ACDF8305F4
online version: 
schema: 2.0.0
---

# Get-AzureRmADSpCredential

## SYNOPSIS
Gets a list of credentials associated with a service principal.

## SYNTAX

### ObjectIdParameterSet (Default)
```
Get-AzureRmADSpCredential -ObjectId <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### SPNParameterSet
```
Get-AzureRmADSpCredential -ServicePrincipalName <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmADSpCredential** cmdlet gets a list of credentials associated with a service principal.
This command gets all of the credential properties, but not the credential value, associated with the service principal.

## EXAMPLES

### Example 1: Get a list of credentials associated with a service principal

```
PS C:\> Get-AzureRmADSpCredential -ServicePrincipalName "http://test12345"
```

This command gets a list of credentials associated with the service principal having SPN 'http://test12345'.

## PARAMETERS

### -ObjectId
Specifies the object ID of the service principal that this cmdlet gets credentials from.

```yaml
Type: String
Parameter Sets: ObjectIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

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

### -ServicePrincipalName
Specifies the name of the service principal name (SPN) that this cmdlet gets credentials from.

```yaml
Type: String
Parameter Sets: SPNParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmADSpCredential](./New-AzureRmADSpCredential.md)

[Remove-AzureRmADSpCredential](./Remove-AzureRmADSpCredential.md)

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)
