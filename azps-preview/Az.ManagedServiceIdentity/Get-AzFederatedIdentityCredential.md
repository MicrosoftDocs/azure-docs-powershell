---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.ManagedServiceIdentity.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.ManagedServiceIdentity
ms.date: 10/29/2026
PlatyPS schema version: 2024-05-01
title: Get-AzFederatedIdentityCredential
---

# Get-AzFederatedIdentityCredential

## SYNOPSIS

Gets one, or lists all, federated identity credentials on a user-assigned managed identity.

## SYNTAX

### List (Default)

```
Get-AzFederatedIdentityCredential -ResourceGroupName <string> -IdentityName <string>
 [-SubscriptionId <string>] [-Skiptoken <string>] [-Top <int>] [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzFederatedIdentityCredential -ResourceGroupName <string> -IdentityName <string> -Name <string>
 [-SubscriptionId <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Gets a single federated identity credential by name, or lists all federated identity credentials configured on a user-assigned managed identity when -Name is omitted.

## EXAMPLES

### Example 1: List federated credentials on an identity

List all federated identity credentials configured on a user-assigned managed identity.

```powershell
Get-AzFederatedIdentityCredential -ResourceGroupName myResourceGroup -IdentityName myIdentity
```

### Example 2: Get a single federated credential by name

Get the details of a single federated identity credential.

```powershell
Get-AzFederatedIdentityCredential -ResourceGroupName myResourceGroup -IdentityName myIdentity -Name myFederatedCredential
```

## PARAMETERS

### -IdentityName

The name of the user-assigned managed identity.

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

### -Name

The name of the federated identity credential resource.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
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

### -Skiptoken

A skip token is used to continue retrieving items after an operation returns a partial result.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
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

### -Top

Number of records to return.

```yaml
Type: System.Nullable`1[System.Int32]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
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

The matching federated identity credential(s).

## NOTES

## RELATED LINKS


- [Get-AzFederatedIdentityCredential](Get-AzFederatedIdentityCredential.md)
- [New-AzFederatedIdentityCredential](New-AzFederatedIdentityCredential.md)
- [Update-AzFederatedIdentityCredential](Update-AzFederatedIdentityCredential.md)
- [Remove-AzFederatedIdentityCredential](Remove-AzFederatedIdentityCredential.md)
