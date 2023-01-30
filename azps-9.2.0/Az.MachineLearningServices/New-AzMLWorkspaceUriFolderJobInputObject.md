---
external help file: 
Module Name: Az.MachineLearningServices
online version: https://docs.microsoft.com/powershell/module/az.MLWorkspace/new-AzMLWorkspaceUriFolderJobInputObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceUriFolderJobInputObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceUriFolderJobInputObject.md
---

# New-AzMLWorkspaceUriFolderJobInputObject

## SYNOPSIS
Create an in-memory object for UriFolderJobInput.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.machinelearningservices/new-azmlworkspaceurifolderjobinputobject) for up-to-date information.

## SYNTAX

```
New-AzMLWorkspaceUriFolderJobInputObject -Type <JobInputType> -Uri <String> [-Description <String>]
 [-Mode <InputDeliveryMode>] [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for UriFolderJobInput.

## EXAMPLES

### Example 1: Create an in-memory object for UriFolderJobInput
```powershell
New-AzMLWorkspaceUriFolderJobInputObject
```

Create an in-memory object for UriFolderJobInput

## PARAMETERS

### -Description
Description for the input.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Input Asset Delivery Mode.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Support.InputDeliveryMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
[Required] Specifies the type of job.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Support.JobInputType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri
[Required] Input Asset URI.

```yaml
Type: System.String
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

### Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Models.Api20220501.UriFolderJobInput

## NOTES

ALIASES

## RELATED LINKS
