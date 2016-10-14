---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=324179
schema: 2.0.0
---

# New-AzureMediaServicesKey

## SYNOPSIS
Updates Azure Media Services account keys.

## SYNTAX

```
New-AzureMediaServicesKey [-Name] <String> [-KeyType] <MediaServicesKeyType> [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The `New-AzureMediaServicesKey` cmdlet updates the Primary or Secondary key for the specified Media Services account.

## EXAMPLES

### 1: Update a Media Services account key
```
PS C:\> New-AzureMediaServicesKey -Name "mediaservicesaccount" -KeyType "Primary" -Force
```

## PARAMETERS

### -Name
The name of the Media Services account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyType
The Media Services key type \<Primary|Secondary\>.

```yaml
Type: MediaServicesKeyType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
If the ` ¢â‚¬"Force` switch is specified, the key generation is not confirmed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[How to use Azure PowerShell for Media Services](http://go.microsoft.com/fwlink/?LinkId=324179)

