---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnedgenode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
---

# Get-AzCdnEdgeNode

## SYNOPSIS
Gets Azure CDN edgenodes.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.cdn/get-azcdnedgenode) for up-to-date information.

## SYNTAX

```
Get-AzCdnEdgeNode [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzCdnEdgeNode** cmdlet gets Azure CDN edgenodes.

## EXAMPLES

### Example 1
```powershell
(Get-AzCdnEdgeNode).IpAddressGroups[0] | ConvertTo-Json
```

```Output
{
  "DeliveryRegion": "All",
  "Ipv4Addresses": [
    {
      "BaseIpAddress": "23.200.152.0",
      "PrefixLength": 21
    }
  ],
  "Ipv6Addresses": [
    {
      "BaseIpAddress": "2600:1417:9800::",
      "PrefixLength": 48
    }
  ]
}
```

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.EdgeNodes.PSEdgeNode

## NOTES

## RELATED LINKS
