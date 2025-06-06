---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/Az.Cdn/new-azcdnpurgeparametersobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnPurgeParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnPurgeParametersObject.md
---

# New-AzCdnPurgeParametersObject

## SYNOPSIS
Create an in-memory object for PurgeParameters.

## SYNTAX

```
New-AzCdnPurgeParametersObject -ContentPath <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for PurgeParameters.

## EXAMPLES

### Example 1: Create an in-memory object for PurgeParameters
```powershell
$contentPath = @("/movies/amazing.mp4","/pictures/pic1.jpg")
New-AzCdnPurgeParametersObject -ContentPath $contentPath
```

```output
ContentPath
-----------
{/movies/amazing.mp4, /pictures/pic1.jpg}
```

Create an in-memory object for PurgeParameters

## PARAMETERS

### -ContentPath
The path to the content to be purged.
Can describe a file path or a wild card directory.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.PurgeParameters

## NOTES

## RELATED LINKS
