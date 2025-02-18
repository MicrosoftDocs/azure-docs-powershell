---
description: Learn about the impact of mandatory multifactor authentication enforcement on Azure PowerShell in automation scenarios
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: The impact of multifactor authentication on Azure PowerShell in automation scenarios
---

# The impact of multifactor authentication on Azure PowerShell in automation scenarios

This article explores how multifactor authentication (MFA) affects automation tasks that use
Microsoft Entra user identities and provides guidance on alternative approaches for uninterrupted
automation.

> [!IMPORTANT]
> Action is required if you're using Microsoft Entra user identities for automation.

MFA requirements prevent you from using Microsoft Entra user identities for authentication in
automation scenarios. Organizations must switch to authentication methods designed for automation,
such as managed identities or service principals, which support non-interactive automation use
cases.

## Limitations of user identities with MFA in automation

> [!NOTE]
> You might encounter the error message: **Interactive authentication is needed** when using a user
> identity with automation.

- **Interactive authentication**: MFA is triggered during interactive sign-ins when using a
  Microsoft Entra user identity. For automation scripts relying on a user identity, MFA disrupts the
  process because it requires extra verification steps. For example, authenticator app, phone call,
  etc., that you can't automate. This verification prevents automation from running unless
  authentication is handled in a non-interactive way, such as with a managed identity or service
  principal.

- **Scripted login failures**: In automation scenarios like running Azure PowerShell scripts
  unattended, an MFA-enabled user identity causes the script to fail when trying to authenticate.
  Since MFA requires user interaction, it's incompatible with non-interactive scripts. This means
  you must switch to a managed identity or service principal, both of which use non-interactive
  authentication.

- **Security considerations**: While MFA adds an extra layer of security, it can limit automation
  flexibility, especially in production environments where automation must run without manual
  intervention. Shifting to managed identities, service principals, or federated identities, which
  are designed for automation purposes and don't require MFA, is more practical and secure in such
  environments.

## Scenarios that require updates

The following list provides example scenarios where customers might use a Microsoft Entra user
identity for automation with Azure PowerShell. This list isn't exhaustive of all scenarios.

> [!WARNING]
> Any automation scenario that uses a Microsoft Entra user identity requires updating.

- **Personalized or specific permissions**: Automation tasks that require user-specific permissions,
  such as actions tied to an individual's role or specific Microsoft Entra ID attributes.

- **OAuth 2.0 ROPC flow**: The OAuth 2.0 Resource Owner Password Credentials (ROPC) token grant flow
  is incompatible with MFA. Automation scenarios using ROPC for authentication fail when MFA is
  required, as MFA can't be completed in a non-interactive flow.

- **Access to resources external to Azure**: Automation scenarios that require access to Microsoft
  365 resources. For example, SharePoint, Exchange, or other cloud services tied to an individual
  user's Microsoft account.

- **Service accounts synced from Active Directory to Microsoft Entra ID**: Organizations using
  service accounts synced from Active Directory (AD) to Microsoft Entra ID. It's important to note
  that these accounts are also subject to MFA requirements and trigger the same issues as other user
  identities.

- **User context for auditing or compliance**: Cases where the actions needed to be auditable at an
  individual user level for compliance reasons.

- **Simple configuration for small-scale or low-risk automation**: For small-scale or low-risk
  automation tasks. For example, a script that manages a few resources.

- **User-driven automation in nonproduction environments**: If the automation is intended for
  personal or nonproduction environments where an individual user is responsible for a task.

- **Automation within a user's own Azure subscription**: If a user needs to automate tasks in their
  own Azure subscription where the user already has sufficient permissions.

Switching to a managed identity or service principal is required for automation scenarios due to
mandatory MFA enforcement for Microsoft Entra user identities.

## See also

- [Sign in to Azure PowerShell non-interactively for automation scenarios][noninteractive-auth]
- [Reducing personal access token (PAT) usage across Azure DevOps][pat-ado-blog]
- [Improve security posture in Azure service connections with AzurePipelinesCredential][fic-serviceconn-blog]

### Managed identities

- [Managed identities for Azure resources][managed-identities]

### Service principals

- [Securing service principals in Microsoft Entra ID][service-principals-entra]
- [Apps & service principals in Microsoft Entra ID][apps-sp-entra]

### Workload identities

- [Workload identities, other machine identities, and human identities][workload-identities]

### Federated identities

- [Flexible federated identity credentials (preview)][federated-identities]
- [Configure an application to trust a managed identity (preview)][trust-managed-identity]
- [Set up a Flexible Federated identity credential (preview)][setup-federated-identity]
- [Migrate to Microsoft Entra multifactor authentication with federations][mfa-federations]

### Microsoft Entra MFA articles

- [Plan for mandatory Microsoft Entra multifactor authentication (MFA)][plan-entra-mfa]
- [How to use the MFA Server Migration Utility to migrate to Microsoft Entra multifactor authentication][mfa-migrate-util]
- [Configure Microsoft Entra multifactor authentication][config-entra-mfa]
- [Deployment considerations for Microsoft Entra multifactor authentication][deploy-considerations-entra-mfa]
- [Migrate from MFA Server to Microsoft Entra multifactor authentication][migrate-mfa-server-entra]

<!-- link references -->

[noninteractive-auth]: /powershell/azure/authenticate-noninteractive
[pat-ado-blog]: https://devblogs.microsoft.com/devops/reducing-pat-usage-across-azure-devops/
[fic-serviceconn-blog]: https://devblogs.microsoft.com/azure-sdk/improve-security-posture-in-azure-service-connections-with-azurepipelinescredential/

[managed-identities]: /entra/identity/managed-identities-azure-resources/

[service-principals-entra]: /entra/architecture/service-accounts-principal
[apps-sp-entra]: /entra/identity-platform/app-objects-and-service-principals

[workload-identities]: /entra/workload-id/workload-identities-overview#workload-identities-other-machine-identities-and-human-identities

[federated-identities]: /entra/workload-id/workload-identities-flexible-federated-identity-credentials
[trust-managed-identity]: /entra/workload-id/workload-identity-federation-config-app-trust-managed-identity
[setup-federated-identity]: /entra/workload-id/workload-identities-set-up-flexible-federated-identity-credential
[mfa-federations]: /entra/identity/authentication/how-to-migrate-mfa-server-to-mfa-with-federation

[plan-entra-mfa]: /entra/identity/authentication/concept-mandatory-multifactor-authentication
[mfa-migrate-util]: /entra/identity/authentication/how-to-mfa-server-migration-utility
[config-entra-mfa]: /entra/identity/authentication/howto-mfa-mfasettings
[deploy-considerations-entra-mfa]: /entra/identity/authentication/howto-mfa-getstarted
[migrate-mfa-server-entra]: /entra/identity/authentication/how-to-migrate-mfa-server-to-azure-mfa
