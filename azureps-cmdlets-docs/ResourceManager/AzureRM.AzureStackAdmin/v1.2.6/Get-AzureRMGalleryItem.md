---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: D25D1FAB-E24C-40E6-931D-BA7E54E33283
---

# Get-AzureRMGalleryItem

## SYNOPSIS
Get the gallery item.

## SYNTAX

```
Get-AzureRMGalleryItem [-Name <String>] [-SubscriptionId <Guid>] [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmGalleryItem** cmdlet gets the gallery item.

## EXAMPLES

### Example 1: Get a gallery item
```
Get-AzureRMGalleryItem -Name "Microsoft.SqlDatabase.0.1.0" -ApiVersion "2015-04-01"
```

Description

-----------

The command gets the gallery item named Microsoft.SqlDatabase.0.1.0.

## PARAMETERS

### -AdminUri
Specifies the Azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against Azure active directory.
This parameter will be deprecated in future.

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
Specifies the API version supported.
The *ApiVersion* parameter needs to be 2015-04-01.
This parameter will be deprecated in future.

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

### -InformationAction
Specifies how this cmdlet responds to an information event.
The acceptable values for this parameter are:
* Continue
* Ignore
* Inquire
* SilentlyContinue
* Stop
* Suspend

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

### -Name
Specifies the gallery item name that this cmdlet gets.

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

### -PipelineVariable
Stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.

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
Specifies the service administrator subscription ID.
This parameter is not needed when using the cmdlet against the Azure stack environment configured against Azure active directory.
This parameter will be deprecated in a future release.

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
Specifies the authentication token for making the request.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in a future release.

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

### Microsoft.AzureStack.Management.Models.GalleryItemModel

## NOTES

## RELATED LINKS

[Add-AzureRmGalleryItem](./Add-AzureRmGalleryItem.md)

[Remove-AzureRmGalleryItem](./Remove-AzureRmGalleryItem.md)
