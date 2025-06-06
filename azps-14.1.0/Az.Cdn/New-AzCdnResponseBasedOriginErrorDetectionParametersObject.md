---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/Az.Cdn/new-azcdnresponsebasedoriginerrordetectionparametersobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnResponseBasedOriginErrorDetectionParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnResponseBasedOriginErrorDetectionParametersObject.md
---

# New-AzCdnResponseBasedOriginErrorDetectionParametersObject

## SYNOPSIS
Create an in-memory object for ResponseBasedOriginErrorDetectionParameters.

## SYNTAX

```
New-AzCdnResponseBasedOriginErrorDetectionParametersObject [-HttpErrorRange <IHttpErrorRangeParameters[]>]
 [-ResponseBasedDetectedErrorType <String>] [-ResponseBasedFailoverThresholdPercentage <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for ResponseBasedOriginErrorDetectionParameters.

## EXAMPLES

### Example 1: Create an in-memory object for ResponseBasedOriginErrorDetectionParameters
```powershell
New-AzCdnResponseBasedOriginErrorDetectionParametersObject -ResponseBasedDetectedErrorType testDetctedError -ResponseBasedFailoverThresholdPercentage 6
```

```output
ResponseBasedDetectedErrorType ResponseBasedFailoverThresholdPercentage
------------------------------ ----------------------------------------
testDetctedError               6
```

Create an in-memory object for ResponseBasedOriginErrorDetectionParameters

## PARAMETERS

### -HttpErrorRange
The list of Http status code ranges that are considered as server errors for origin and it is marked as unhealthy.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.IHttpErrorRangeParameters[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseBasedDetectedErrorType
Type of response errors for real user requests for which origin will be deemed unhealthy.

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

### -ResponseBasedFailoverThresholdPercentage
The percentage of failed requests in the sample where failover should trigger.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ResponseBasedOriginErrorDetectionParameters

## NOTES

## RELATED LINKS
