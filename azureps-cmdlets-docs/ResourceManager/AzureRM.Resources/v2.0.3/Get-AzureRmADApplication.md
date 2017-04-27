---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmADApplication

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADApplication
```

### ApplicationObjectIdParameterSet
```
Get-AzureRmADApplication -ApplicationObjectId <Guid>
```

### ApplicationIdParameterSet
```
Get-AzureRmADApplication -ApplicationId <Guid>
```

### ApplicationDisplayNameParameterSet
```
Get-AzureRmADApplication -DisplayNameStartWith <String>
```

### ApplicationIdentifierUriParameterSet
```
Get-AzureRmADApplication -IdentifierUri <String>
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ApplicationId
The application id.

```yaml
Type: Guid
Parameter Sets: ApplicationIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationObjectId
The application object id.

```yaml
Type: Guid
Parameter Sets: ApplicationObjectIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayNameStartWith
The display name.

```yaml
Type: String
Parameter Sets: ApplicationDisplayNameParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentifierUri
The identifierUri of the application.

```yaml
Type: String
Parameter Sets: ApplicationIdentifierUriParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.Guid
System.String


## OUTPUTS

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Resources.Models.ActiveDirectory.PSADApplication, Microsoft.Azure.Commands.Resources, Version=2.0.3.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]


## NOTES

## RELATED LINKS

