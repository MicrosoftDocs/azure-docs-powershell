---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureSBNamespace

## SYNOPSIS
Creates a namespace.

## SYNTAX

```
New-AzureSBNamespace [-Name] <String> [[-Location] <String>] [[-CreateACSNamespace] <Boolean>]
 [-NamespaceType] <NamespaceType> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **New-AzureSBNamespace** cmdlet creates a service namespace for use with Service Bus in Azure.

## EXAMPLES

### 1: Create a service namespace
```
PS C:\> New-AzureSBNamespace -name myNameSpace -Location East US PS C:\> New-AzureSBNamespace myNameSpace 'East US'
```

The following examples create a service namespace for use with Service Bus in Azure.
Both examples include the required parameter values, but only the first includes the parameter names.
The second example can be used because both parameters are positional and their values are given in the required order.

## PARAMETERS

### -Name
Specifies a name for the new namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies a region for the new namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreateACSNamespace
Specifies whether to create an associated ACS namespace in addition to the service namespace.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NamespaceType
Specify a whether to use the namespace for Messaging or Notification Hubs.

```yaml
Type: NamespaceType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureSBNamespace](.\Remove-AzureSBNamespace.md)

