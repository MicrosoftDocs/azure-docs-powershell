---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.ManagedServiceIdentity.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.ManagedServiceIdentity
ms.date: 10/29/2026
PlatyPS schema version: 2024-05-01
title: New-AzFederatedIdentityCredential
---

# New-AzFederatedIdentityCredential

## SYNOPSIS

Creates a federated identity credential on a user-assigned managed identity.

## SYNTAX

### Default (Default)

```
New-AzFederatedIdentityCredential -ResourceGroupName <string> -IdentityName <string> -Name <string>
 [-SubscriptionId <string>] [-Audience <string[]>] [-Issuer <string>] [-Subject <string>]
 [-ClaimsMatchingExpressionVersion <int>] [-ClaimsMatchingExpressionValue <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Creates a federated identity credential that trusts an external OIDC issuer, so a workload presenting a matching token can exchange it for a Microsoft Entra access token on behalf of the managed identity. Specify either -Subject or the ClaimsMatchingExpression parameters, but not both.

## EXAMPLES

### Example 1: Create a federated credential using a subject

Create a federated identity credential that trusts a Kubernetes service account.

```powershell
New-AzFederatedIdentityCredential -ResourceGroupName myResourceGroup -IdentityName myIdentity -Name myFederatedCredential -Issuer https://kubernetes-oauth.azure.com -Subject system:serviceaccount:ns:svcaccount -Audience api://AzureADTokenExchange
```

### Example 2: Create a federated credential for GitHub Actions using a claims matching expression

Trust GitHub Actions tokens for the `main` branch of `contoso/my-repo` using a claims matching expression.

```powershell
New-AzFederatedIdentityCredential -ResourceGroupName myResourceGroup -IdentityName myIdentity -Name myFederatedCredential -Issuer https://token.actions.githubusercontent.com -ClaimsMatchingExpressionVersion 1 -ClaimsMatchingExpressionValue "claims['sub'] eq 'repo:contoso/my-repo:ref:refs/heads/main'" -Audience api://AzureADTokenExchange
```

## PARAMETERS

### -Audience

The list of audiences that can appear in the issued token. Defaults to `api://AzureADTokenExchange` when omitted.

```yaml
Type: System.String[]
DefaultValue: ''
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
HelpMessage: ''
```

### -ClaimsMatchingExpressionValue

The expression for matching incoming claims. Cannot be used with -Subject.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -ClaimsMatchingExpressionVersion

The version of the claims matching expression syntax used in -ClaimsMatchingExpressionValue.

```yaml
Type: System.Nullable`1[System.Int32]
DefaultValue: ''
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
HelpMessage: ''
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- cf
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -IdentityName

The name of the user-assigned managed identity to add the federated credential to.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Issuer

The URL of the external identity provider to be trusted. Must match the `iss` claim of tokens presented for exchange.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -Name

The name of the federated identity credential resource.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Use the named profile for this command, overriding the active profile.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -ResourceGroupName

The name of the resource group containing the user-assigned managed identity.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Subject

The identifier of the external software workload. Must match the `sub` claim of tokens presented for exchange. Cannot be used with -ClaimsMatchingExpressionValue.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -SubscriptionId

Name or ID of the subscription. Defaults to the active profile's subscription.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### -WhatIf

Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- wi
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.ManagedServiceIdentity.Models.FederatedIdentityCredential

The created federated identity credential.

## NOTES

## RELATED LINKS


- [Get-AzFederatedIdentityCredential](Get-AzFederatedIdentityCredential.md)
- [Update-AzFederatedIdentityCredential](Update-AzFederatedIdentityCredential.md)
- [Remove-AzFederatedIdentityCredential](Remove-AzFederatedIdentityCredential.md)
