---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
ms.assetid: AD76C752-2070-449D-BF4F-B4260B05AB02
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Update-AzureRmSiteRecoveryServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Update-AzureRmSiteRecoveryServer.md
gitcommit: https://github.com/Azure/azure-powershell/blob/173e94aec59d7f539b72e43e90e5e7f8ba5f62bc
---

# Update-AzureRmSiteRecoveryServer

## SYNOPSIS
Refreshes a Site Recovery server.

## SYNTAX

```
Update-AzureRmSiteRecoveryServer -Server <ASRServer> [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureRmSiteRecoveryServer** cmdlet refreshes an Azure Site Recovery server.

## EXAMPLES

## PARAMETERS

### -Server
Specifies the Site Recovery server that this cmdlet updates.

```yaml
Type: ASRServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### ASRServer

Parameter 'Server' accepts value of type 'ASRServer' from the pipeline

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmSiteRecoveryServer](./Get-AzureRmSiteRecoveryServer.md)

[Remove-AzureRmSiteRecoveryServer](./Remove-AzureRmSiteRecoveryServer.md)
