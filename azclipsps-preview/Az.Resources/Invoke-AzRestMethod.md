---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Resources
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Invoke-AzRestMethod
---

# Invoke-AzRestMethod

## SYNOPSIS

Send an authenticated REST request to Azure Resource Manager and return the raw response.

## SYNTAX

### \_\_AllParameterSets

```
Invoke-AzRestMethod [-Method <string>] [-Uri <string>] [-Payload <string>] [-Headers <Object>]
 [-SubscriptionId <string>] [-ResourceGroupName <string>] [-ResourceProviderName <string>]
 [-ResourceType <string[]>] [-Name <string[]>] [-ApiVersion <string>] [-UriParameters <Object>]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

`Invoke-AzRestMethod` is a universal authenticated ARM REST passthrough, mirroring `az rest` and `Invoke-AzRestMethod`. It sends an arbitrary HTTP request through the already-authenticated AzClips pipeline to Azure Resource Manager and returns the raw response: the HTTP status code, the response headers, and the response body. When the response body is JSON, a parsed `Json` representation is also returned alongside the raw content.

The target URL can be supplied two ways. In **Uri mode**, pass `-Uri` with an absolute ARM URL or a relative ARM path (relative paths are prefixed with `https://management.azure.com`, and the token `{subscriptionId}` is replaced with the current subscription). In **ByParameters mode**, build the URL piece-wise from `-SubscriptionId`, `-ResourceGroupName`, `-ResourceProviderName`, `-ResourceType`, `-Name`, and `-ApiVersion`. The two modes are mutually exclusive.

This cmdlet performs no long-running-operation polling and no automatic pagination, and it targets the Azure Resource Manager audience only. Use it to call ARM endpoints that do not yet have a dedicated cmdlet.

## EXAMPLES

### Example 1: List resource groups in a subscription (Uri mode)

Send a `GET` to an absolute ARM path and read the parsed JSON from the response.

```powershell
Invoke-AzRestMethod -Method GET -Uri "/subscriptions/{subscriptionId}/resourcegroups?api-version=2021-04-01"
```

### Example 2: Get a resource group built from parameters (ByParameters mode)

Build the ARM URL piece-wise instead of passing a full URI. The default method is `GET`.

```powershell
Invoke-AzRestMethod -ResourceGroupName myRg -ApiVersion 2021-04-01
```

### Example 3: Create or update a resource group with a JSON payload

Send a `PUT` with a request body and a custom header.

```powershell
Invoke-AzRestMethod -Method PUT -Uri "/subscriptions/{subscriptionId}/resourcegroups/myRg?api-version=2021-04-01" -Payload '{"location":"eastus"}' -Headers @{ 'Content-Type' = 'application/json' }
```

## PARAMETERS

### -ApiVersion

The `api-version` used when building an ARM URL from piece-wise parameters. Required in ByParameters mode. Mutually exclusive with `-Uri`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Headers

Optional request headers, supplied either as a hashtable (`@{ 'Accept' = 'application/json' }`) or as a string array in `KEY=VALUE` form (`'Accept=application/json'`).

```yaml
Type: System.Object
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Method

The HTTP method to use (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, or `OPTIONS`). Defaults to `GET`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Name

Resource name segments, interleaved with `-ResourceType` (may have one fewer entry than `-ResourceType` for a collection GET). Used to build an ARM URL from piece-wise parameters. Mutually exclusive with `-Uri`.

```yaml
Type: System.String[]
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Payload

Optional request body (typically JSON). Sent whenever provided, for any HTTP method.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -ResourceGroupName

Resource group name segment used to build an ARM URL from piece-wise parameters. Mutually exclusive with `-Uri`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -ResourceProviderName

Resource provider namespace (for example, `Microsoft.Resources`) used to build an ARM URL from piece-wise parameters. Mutually exclusive with `-Uri`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -ResourceType

Resource type segments, interleaved with `-Name`, used to build an ARM URL from piece-wise parameters. Mutually exclusive with `-Uri`.

```yaml
Type: System.String[]
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -SubscriptionId

Subscription id used to build an ARM URL from piece-wise parameters. Defaults to the current subscription. Mutually exclusive with `-Uri`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Uri

Absolute URL or relative ARM path for the request. Relative paths are prefixed with `https://management.azure.com`, and the token `{subscriptionId}` is replaced with the current subscription. Mutually exclusive with the piece-wise ByParameters inputs (`-SubscriptionId`, `-ResourceGroupName`, `-ResourceProviderName`, `-ResourceType`, `-Name`, `-ApiVersion`).

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -UriParameters

Optional query-string parameters, supplied either as a hashtable (`@{ '$top' = '3' }`) or as a string array in `KEY=VALUE` form (`'$top=3'`). Appended to the final URL in either mode.

```yaml
Type: System.Object
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.RestResponse

A `RestResponse` object containing the HTTP status code, response headers, parsed JSON body (when applicable), and raw body text.

## NOTES

This cmdlet targets the Azure Resource Manager audience only. It does not poll long-running operations and does not page through `nextLink` results; for paged endpoints, follow the returned `nextLink` yourself with another call.

## RELATED LINKS

- [Get-AzResourceGroup]()
- [New-AzResourceGroupDeployment]()
