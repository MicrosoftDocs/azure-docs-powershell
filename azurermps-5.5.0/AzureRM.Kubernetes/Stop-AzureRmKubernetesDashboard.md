---
Module Name: AzureRM.Kubernetes
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Kubernetes/Commands.Kubernetes/help/Stop-AzureRmKubernetesDashboard.md
external help file: Microsoft.Azure.Commands.Kubernetes.dll-Help.xml
online version: https://docs.microsoft.com/en-us/powershell/
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Kubernetes/Commands.Kubernetes/help/Stop-AzureRmKubernetesDashboard.md
schema: 2.0.0
---

# Stop-AzureRmKubernetesDashboard

## SYNOPSIS
Stop the Kubectl SSH tunnel created in Start-AzureRmKubernetesDashboard.

## SYNTAX

```
Stop-AzureRmKubernetesDashboard [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Stop the Kubectl SSH tunnel created in Start-AzureRmKubernetesDashboard.

## EXAMPLES

### Example 1
```
PS C:\> Stop-AzureRmKubernetesDashboard
```

Stops the existing SSH tunnel setup by executing Start-AzureRmKubernetesDashboard.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## NOTES

## RELATED LINKS