---
description: Strategies to manage, protect, and prevent inadvertent exposure of secrets and sensitive information in Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Protect secrets in Azure PowerShell
---

# Protect secrets in Azure PowerShell

When you manage Azure resources with Azure PowerShell, the output of commands might expose sensitive
information that you must protect. For example, Azure PowerShell could display passwords, tokens, or
keys in the output when you create them. Some commands can also store the output in log files. This
scenario is often the case when working with GitHub Actions or Azure DevOps.

## Understand the risk

It's critical to protect secrets and sensitive information. When mishandled, they can become
accessible to unauthorized users. User errors, such as improperly configured scripts or entering
secrets in plain text as values for parameters, can expose sensitive details in logs, command
history, or version control systems.

## Warning message

Azure PowerShell displays a warning message by default beginning with version 12.0.0 to help you
protect sensitive information when it identifies a potential secret in the output of a command.

### Disable the warning message

In the following example, the `Update-AzConfig` cmdlet is used to disable the warning message.

```azurepowershell-interactive
Update-AzConfig -DisplaySecretsWarning $false
```

You can also use the `$Env:AZURE_CLIENTS_SHOW_SECRETS_WARNING` environment variable to disable the
warning message.

```azurepowershell
Set-Item -Path Env:\AZURE_CLIENTS_SHOW_SECRETS_WARNING -Value $false
```

## Transition from Strings to SecureStrings

To improve security and reduce the risk of credential leaks, the default output type of the
`Get-AzAccessToken` cmdlet changed from a plain text `String` to a `SecureString`, starting with
**Az.Accounts** version 5.0.0 and **Az** version 14.0.0.

Access tokens are sensitive credentials that grant access to Azure resources. Returning them as
plain text increases the risk of accidental exposure in logs, transcripts, or interactive sessions.
By switching to `SecureString`, the cmdlet helps prevent tokens from being displayed or stored
insecurely.

If your scenario requires the token in plain text, which is strongly discouraged, you can convert
the `SecureString` manually. For guidance, see
[How can I convert a SecureString to plain text in PowerShell?][convert-secure-string-to-string].

<!-- link references -->

[convert-secure-string-to-string]: /powershell/azure/faq#how-can-i-convert-a-securestring-to-plain-text-in-powershell-
