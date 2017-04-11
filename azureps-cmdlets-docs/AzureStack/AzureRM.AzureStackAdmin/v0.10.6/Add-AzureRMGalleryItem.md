---
external help file: Microsoft.AzureStack.Commands.dll-help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRMGalleryItem

## SYNOPSIS
The Add-AzureRMGalleryItem cmdlet adds the gallery item package.
The gallery item uri needs to be a http/https uri accessible to the gallery service. 
Typically .azpkg file is uploaded to a publicly accessible blob container and its uri is provided as the GallelryItemUri parameter

## SYNTAX

```
Add-AzureRMGalleryItem -GalleryItemUri <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Add-AzureRMGalleryItem -ApiVersion 2015-04-01 -GalleryItemUri "http://127.0.0.1:10000/devstoreaccount1/sqlrpgallery/Microsoft.SqlDatabase.0.1.0.azpkg"
```

Description

-----------

The example uploads and registers the gallery package with the gallery service

## PARAMETERS

### -GalleryItemUri
The http/https uri containing the .azpkg file.
The Uri should be accessible to the gallery service

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
Not Specified

The following values are permitted for this object type.

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
Not Specified

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
Not Specified

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

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## NOTES

## RELATED LINKS

