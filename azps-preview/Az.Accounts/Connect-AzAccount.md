---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Accounts.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Accounts
ms.date: 10/28/2026
PlatyPS schema version: 2024-05-01
title: Connect-AzAccount
---

# Connect-AzAccount

## SYNOPSIS

Authenticate to Azure.

## SYNTAX

### Default (Default)

```
Connect-AzAccount [-SubscriptionId <string>] [-TenantId <string>] [-UseDeviceCode]
 [-OutProfile <string>] [-Profile <string>] [-Identity] [-ClientId <string>] [-ObjectId <string>]
 [-ResourceId <string>] [-ServicePrincipal] [-FederatedToken <string>]
 [-ClientSecret <securestring>] [-Credential <pscredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Authenticate to Azure and persist account context for subsequent commands.

For service principal client-secret sign-in, use either `-ClientId` with
`-ClientSecret <SecureString>`, or the backward-compatible `-ServicePrincipal`
with `-Credential <PSCredential>` syntax. The credential username is the application
ID and its password is the client secret. Both forms use the same authentication flow.

Initial service principal sign-in requires a tenant ID and an explicit subscription ID.
Login does not inherit argument defaults from the current profile. Client-secret arguments
can't be combined with managed identity, device-code authentication, a federated token,
or `-Profile`. Use `-OutProfile` to save a named profile.

Managed identity sign-in also requires a subscription ID, supplied with `-SubscriptionId`. The managed identity environment determines the tenant; don't supply `-TenantId` with `-Identity`.

## EXAMPLES

### Sign in with the default browser flow

Launches the interactive browser sign-in experience and persists the resulting account context for the specified subscription. Use this on a workstation with a default browser available.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '00000000-0000-0000-0000-000000000000'
```

### Create a named profile

Save the subscription and tenant context as `dev` and make it the active profile.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '00000000-0000-0000-0000-000000000000' -OutProfile dev
```

### Switch the active profile

Sign in as `dev`, then switch to an already saved `prod` profile for subsequent commands. The `prod` profile can use a different subscription and tenant.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '00000000-0000-0000-0000-000000000000' -OutProfile dev
Set-AzProfile -Name prod
Get-AzResourceGroup
```

### Use a profile for one command

Sign in as `dev`, then use an already saved `prod` profile's subscription and tenant for one command, leaving `dev` active.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '00000000-0000-0000-0000-000000000000' -OutProfile dev
Get-AzResourceGroup -Profile prod
```

### Sign in with device code on a host without a browser

Uses the device-code authentication flow — prints a code and verification URL to the console so you can complete the sign-in from another device. Useful for SSH sessions, containers, and headless build agents.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '00000000-0000-0000-0000-000000000000' -UseDeviceCode
```

### Sign in with a service principal client secret

Read the secret as a `SecureString` and supply the application ID separately.
The `-ServicePrincipal` switch is optional with `-ClientSecret`.

```powershell
$clientSecret = $Host.UI.ReadLineAsSecureString()
Connect-AzAccount -ClientId '00000000-0000-0000-0000-000000000000' -ClientSecret $clientSecret -Tenant '00000000-0000-0000-0000-000000000000' -Subscription '00000000-0000-0000-0000-000000000000' -OutProfile ci
```

### Sign in with a backward-compatible service principal credential

Create a `PSCredential` whose username is the application ID and whose password
is the client secret. This form requires `-ServicePrincipal`; don't also pass
`-ClientId` or `-ClientSecret`.

```powershell
$clientSecret = $Host.UI.ReadLineAsSecureString()
$credential = [System.Management.Automation.PSCredential]::new('00000000-0000-0000-0000-000000000000', $clientSecret)
Connect-AzAccount -ServicePrincipal -Credential $credential -Tenant '00000000-0000-0000-0000-000000000000' -Subscription '00000000-0000-0000-0000-000000000000' -OutProfile ci
```

### Re-authenticate a client-secret profile

Use the saved client secret to sign in again without supplying new credentials.
This example uses the profile saved by either service principal example above.

```powershell
Connect-AzAccount -Profile ci
```

### Sign in with a managed identity

Sign in using a managed identity. This is typically used when running in an Azure environment that supports managed identities, such as an Azure VM, App Service, or Function App. Tenant ID will be resolved automatically from the environment.

```powershell
Connect-AzAccount -Identity -SubscriptionId '00000000-0000-0000-0000-000000000000'
```

### Sign in with a user-assigned managed identity

Select a user-assigned identity by client ID and persist the specified subscription.

```powershell
Connect-AzAccount -Identity -ClientId '00000000-0000-0000-0000-000000000000' -SubscriptionId '00000000-0000-0000-0000-000000000000'
```

## PARAMETERS

### -ClientId

Application ID of the service principal when used with `-ClientSecret` or
`-ServicePrincipal -FederatedToken`. With `-Identity`, selects a user-assigned managed
identity and is mutually exclusive with `-ObjectId` and `-ResourceId`.
Can't be combined with `-Credential`, which already supplies the application ID.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- AccountId
- ApplicationId
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

### -ClientSecret

Nonempty client secret for the service principal, supplied as a `SecureString`.
Use with `-ClientId`, `-TenantId`, and a subscription ID; `-ServicePrincipal` is optional.
Plain-text strings aren't accepted. Can't be combined with `-Credential`,
`-FederatedToken`, another authentication method, or `-Profile`.

```yaml
Type: System.Security.SecureString
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

### -Credential

Service principal credentials as a `PSCredential`. The username must be the application
ID and the password must be a nonempty client secret. Requires `-ServicePrincipal`;
username/password user sign-in isn't supported. Can't be combined with `-ClientId`
(including its aliases), `-ClientSecret`, `-FederatedToken`, another authentication
method, or `-Profile`.

```yaml
Type: System.Management.Automation.PSCredential
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

### -FederatedToken

Federated token issued by a trusted external identity provider. The issuer and subject must be configured as a federated credential on the application.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ClientAssertion
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

### -Identity

Sign in using a managed identity. System-assigned by default; combine with `-ClientId`, `-ObjectId`, or `-ResourceId` to select a specific user-assigned identity.
Requires an explicit subscription ID supplied with `-SubscriptionId`.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- MSI
- ManagedIdentity
- ManagedService
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

### -ObjectId

Object (principal) ID of the user-assigned managed identity. Use with `-Identity`. Mutually exclusive with `-ClientId` and `-ResourceId`.

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

### -OutProfile

Name of a new named profile in which to persist the sign-in context. Use `-Profile <name>` on subsequent invocations to switch back to it. Mutually exclusive with `-Profile`.

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

### -Profile

Name of an existing named profile to sign into, using its saved subscription ID.
Mutually exclusive with `-OutProfile` and `-SubscriptionId`.

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

### -ResourceId

Full ARM resource ID of the user-assigned managed identity (`/subscriptions/.../resourceGroups/.../providers/Microsoft.ManagedIdentity/userAssignedIdentities/<name>`). Use with `-Identity`. Mutually exclusive with `-ClientId` and `-ObjectId`.

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

### -ServicePrincipal

Sign in as a service principal using a client secret or federated (OIDC) token.
Required with `-Credential` or with `-ClientId -FederatedToken`. Optional with
`-ClientId -ClientSecret`.

```yaml
Type: System.Management.Automation.SwitchParameter
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

Azure subscription ID. Must be supplied explicitly for initial sign-in, including
managed identities. Can't be combined with `-Profile`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Subscription
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

### -TenantId

Tenant ID to login to.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Tenant
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

### -UseDeviceCode

Use device code flow for authentication.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeviceCode
- DeviceAuth
- Device
- UseDeviceAuthentication
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

### Microsoft.Azure.Azclips.Extensions.Accounts.Models.ProfileResult

The activated profile projection (name, tenant ID, subscription ID, cloud, authentication method) after successful sign-in. The underlying profile is also persisted to the on-disk profile store; use `Get-AzProfile` later to enumerate saved profiles.

## NOTES

Generated help for login.

## RELATED LINKS


- [Online Version]()
