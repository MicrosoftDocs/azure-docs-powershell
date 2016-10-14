---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\Enable-AzureWebsiteDebug.md
schema: 2.0.0
---

# Disable-AzureWebsiteDebug

## SYNOPSIS
Disables the website's debugging

## SYNTAX

```
Disable-AzureWebsiteDebug [-PassThru] [[-Name] <String>] [-Slot <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Disables the website's debugging in Visual Studio

## EXAMPLES

### --------------  Disable website debugging --------------
```
C:\PS>Disable-AzureWebsiteDebug -Name MyWebsite
```

Disables website debugging on website MyWebsite

## PARAMETERS

### -Name
The name of the Azure website

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
The slot name of the Azure website

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

### -PassThru
Flag to return true if succeeded

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

[Enable-AzureWebsiteDebug](.\Enable-AzureWebsiteDebug.md)

[Get-AzureWebsite](.\Get-AzureWebsite.md)

[New-AzureWebsite](.\New-AzureWebsite.md)

[Remove-AzureWebsite](.\Remove-AzureWebsite.md)

[Start-AzureWebsite](.\Start-AzureWebsite.md)

