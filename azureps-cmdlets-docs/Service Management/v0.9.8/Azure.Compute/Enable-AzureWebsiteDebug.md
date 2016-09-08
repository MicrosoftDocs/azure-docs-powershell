---
external help file: SMAzure_Compute.xml
online version: 007cc1d1-12ff-4ef0-a480-39b958aff004
schema: 2.0.0
---

# Enable-AzureWebsiteDebug
## SYNOPSIS
Enables the website's debug

## SYNTAX

```
Enable-AzureWebsiteDebug [[-Name] <String>] [-PassThru] [-Slot <String>] [-Version]
```

## DESCRIPTION
Enables the website's debug feature in Visual Studio

## EXAMPLES

### --------------  Enable debugging of Visual Studio 2013 --------------
```
C:\PS>Enable-AzureWebsiteDebug -Name MyWebsite -Version VS2013
```

Enables debugging on VS 2013

## PARAMETERS

### -Name
The name of the Azure website

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
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
Position: Named
Default value: 
Accept pipeline input: False
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
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
The Visual Studio version

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: VS2012, VS2013

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AzureWebsiteDebug](007cc1d1-12ff-4ef0-a480-39b958aff004)

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

