---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://learn.microsoft.com/powershell/module/az.security/Get-AzSecurityAssessmentMetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecurityAssessmentMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecurityAssessmentMetadata.md
---

# Get-AzSecurityAssessmentMetadata

## SYNOPSIS
Gets security assessments types and metadata in a subscription.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecurityAssessmentMetadata [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SubscriptionLevelResource
```
Get-AzSecurityAssessmentMetadata -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceId
```
Get-AzSecurityAssessmentMetadata -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets security assessments types and metadata in a subscription. Security Assessment metadata include Built-In assessments and custom assessment types that the user can define.

## EXAMPLES

### Example 1
```powershell
Get-AzSecurityAssessmentMetadata
```

Gets all the built in assessments and the custom assessments that were configured on the current subscription.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

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

### -Name
Resource name.

```yaml
Type: System.String
Parameter Sets: SubscriptionLevelResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID of the security resource that you want to invoke the command on.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.AssessmentMetadata.PSSecurityAssessmentMetadata

## NOTES

## RELATED LINKS
