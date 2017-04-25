---
external help file: Microsoft.AzureStack.Commands.dll-help.xml
online version:
schema: 2.0.0
---

# Add-AzureRMGalleryItem

## SYNOPSIS
Adds the gallery item package.

## SYNTAX

```
Add-AzureRMGalleryItem -GalleryItemUri <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRMGalleryItem** cmdlet adds the gallery item package. Typically a .azpkg file is uploaded to a publicly accessible blob container and its URI is provided as the **GallelryItemUri** parameter.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Add-AzureRMGalleryItem -ApiVersion 2015-04-01 -GalleryItemUri "http://127.0.0.1:10000/devstoreaccount1/sqlrpgallery/Microsoft.SqlDatabase.0.1.0.azpkg"
```
This command uploads and registers the gallery package with the gallery service.

## PARAMETERS

### -GalleryItemUri
Specifies the http/https URI of the publicly accessible blob that contains the .azpkg file and is accessible to the gallery service.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Not Specified.

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
Not Specified.

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
Not Specified.

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

### Microsoft.Azure.AzureOperationResponse

## NOTES

## RELATED LINKS
