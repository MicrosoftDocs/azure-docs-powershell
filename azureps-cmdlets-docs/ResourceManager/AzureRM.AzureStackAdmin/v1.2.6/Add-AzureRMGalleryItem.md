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
Add-AzureRMGalleryItem [-SubscriptionId <Guid>] -GalleryItemUri <String> [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
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

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in future

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiVersion
Specifies the api version supported.
The value needs to be  2015-04-01.
This parameter will be deprecated in the future.

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

### -SubscriptionId
Service administrator subscription id.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in a future release

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token
Authentication token for making the request. This parameter is not needed when using.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in a future release

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

## INPUTS

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## NOTES
## RELATED LINKS
