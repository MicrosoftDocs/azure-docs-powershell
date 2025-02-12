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

- **Interactive authentication**: MFA is triggered during interactive sign-ins when using a
  Microsoft Entra user identity. For automation scripts relying on a user identity, MFA disrupts the
  process because it requires extra verification steps. For example, authenticator app, phone call,
  etc. that you can't automate. This verification prevents automation from running unless
  authentication is handled in a non-interactive way, such as with a managed identity or service
  principal.

- **Scripted login failures**: In automation scenarios like running Azure PowerShell scripts
  unattended, an MFA-enabled user identity causes the script to fail when trying to authenticate.
  Since MFA requires user interaction, it's incompatible with non-interactive scripts. This means
  you must switch to a managed identity or service principal, both of which use non-interactive
  authentication.

- **Security considerations**: While MFA adds an extra layer of security, it can limit automation
  flexibility, especially in production environments where automation must run without manual
  intervention. Shifting to managed identities or service principals, which don't require MFA, is
  more practical and secure in such environments.

## Scenarios that require updates

The following list provides example scenarios where customers might use a Microsoft Entra user
identity for automation with Azure PowerShell. This list isn't exhaustive of all scenarios.

> [!WARNING]
> Any automation scenario that uses a Microsoft Entra user identity requires updating.

- **Personalized or specific permissions**: Automation tasks that require user-specific permissions,
  such as actions tied to an individual's role or specific Microsoft Entra ID attributes.

- **Access to resources external to Azure**: Automation scenarios that require access to Microsoft
  365 resources. For example, SharePoint, Exchange, or other cloud services tied to an individual
  user's Microsoft account.

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

- [Planning for mandatory multifactor authentication for Azure and other admin portals][plan-for-mfa]
- [Sign in to Azure PowerShell non-interactively for automation scenarios][noninteractive-auth]
- [Reducing personal access token (PAT) usage across Azure DevOps][pat-ado-blog]
- [Improve security posture in Azure service connections with AzurePipelinesCredential][fic-serviceconn-blog]
- [Managed identities for Azure resources][managed-identities]

<!-- link references -->

[plan-for-mfa]: /entra/identity/authentication/concept-mandatory-multifactor-authentication
[noninteractive-auth]: /powershell/azure/authenticate-noninteractive
[pat-ado-blog]: https://devblogs.microsoft.com/devops/reducing-pat-usage-across-azure-devops/
[fic-serviceconn-blog]: https://devblogs.microsoft.com/azure-sdk/improve-security-posture-in-azure-service-connections-with-azurepipelinescredential/
[managed-identities]: /entra/identity/managed-identities-azure-resources/
