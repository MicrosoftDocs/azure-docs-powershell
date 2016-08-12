---
external help file: SMAzure_Compute.xml
online version: 7d8b6162-ecd4-4b7e-8f17-1e63b6d47fbf
schema: 2.0.0
---

# Disable-AzureWebsiteDebug
## SYNOPSIS
Disables the website's debugging

## SYNTAX

```
Disable-AzureWebsiteDebug [[-Name] <String>] [-PassThru] [-Slot <String>]
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AzureWebsiteDebug](7d8b6162-ecd4-4b7e-8f17-1e63b6d47fbf)

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

