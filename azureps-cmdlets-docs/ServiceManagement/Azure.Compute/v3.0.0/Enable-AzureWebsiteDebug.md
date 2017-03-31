---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 00459AA7-2BA0-41B2-99C9-36E9D4205F3E
---

# Enable-AzureWebsiteDebug

## SYNOPSIS
Enables the website's debug.

## SYNTAX

```
Enable-AzureWebsiteDebug [-PassThru] [-Version] <String> [[-Name] <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Enables the website's debug feature in Visual Studio.

## EXAMPLES

### Enable debugging of Visual Studio 2013
```
PS C:\> Enable-AzureWebsiteDebug -Name MyWebsite -Version VS2013
```

Enables debugging on VS 2013.

## PARAMETERS

### -Name
The name of the Azure website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
The slot name of the Azure website.

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

### -Version
The Visual Studio version.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
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

[Disable-AzureWebsiteDebug](./Disable-AzureWebsiteDebug.md)

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsite](./New-AzureWebsite.md)

[Remove-AzureWebsite](./Remove-AzureWebsite.md)

[Start-AzureWebsite](./Start-AzureWebsite.md)


