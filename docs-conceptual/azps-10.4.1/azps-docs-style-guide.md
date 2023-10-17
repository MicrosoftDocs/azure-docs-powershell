---
description: This article provides the rules of style for writing Azure PowerShell documentation.
ms.custom: devx-track-azurepowershell

ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell docs style guide
---

# Azure PowerShell docs style guide

The following checklist helps ensure scripts and samples that use Azure PowerShell are consistent.

## Version

Because most Microsoft Learn documentation doesn't support multiple product versions, the latest
version of the Az PowerShell module should be referenced in articles. Documentation referencing a
specific version number can become outdated because Azure PowerShell is updated monthly. Only the
last two major versions of the Az PowerShell module are supported by Microsoft. For more
information, see [Azure PowerShell support lifecycle](azureps-support-lifecycle.md)

If cmdlets used in the article are part of a preview module, that module must be explicitly
installed because only GA modules ship as part of the Az PowerShell module.

> [!IMPORTANT]
> Do not use commands from the AzureRM PowerShell module in articles. AzureRM is deprecated.

## Prerequisites

### Include files

- Use one of three Azure PowerShell include files when the article contains commands from the Az
  PowerShell module.
  - [No header](https://github.com/MicrosoftDocs/azure-docs/blob/main/includes/azure-powershell-requirements-no-header.md)
  - [H2 header](https://github.com/MicrosoftDocs/azure-docs/blob/main/includes/azure-powershell-requirements.md)
  - [H3 header](https://github.com/MicrosoftDocs/azure-docs/blob/main/includes/azure-powershell-requirements-h3.md)
- Always place Azure service prerequisites first, followed by Azure PowerShell and Azure Cloud Shell
  instructions. For example, "You must have `Microsoft.Authorization/roleAssignments/write`
  permissions to complete the instructions in this tutorial" should come before
  `azure-powershell-requirements-no-header.md`.

If all commands aren't compatible with Cloud Shell, don't use the include files. Instead, instruct
the user to install Azure PowerShell locally. Include the following text in an H2 Prerequisites
section.

```markdown
- This tutorial requires that you run Azure PowerShell locally:
  - [Install the latest version of the Az PowerShell module](/powershell/azure/install-azure-powershell).
  - Connect to your Azure account using the
    [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet.
```

## Formatting syntax elements in a paragraph

Follow the [PowerShell-Docs style guide](/powershell/scripting/community/contributing/powershell-style-guide)
and [Editor's checklist](/powershell/scripting/community/contributing/editorial-checklist)
for formatting command syntax elements in Azure PowerShell documentation.

The first mention of a cmdlet name should be a link to the cmdlet documentation, for example:

```markdown
The [Get-AzVM](/powershell/module/az.compute/get-azvm) cmdlet uses the **Location** parameter to ...
```

> [!NOTE]
> Do not format text inside the brackets of a hyperlink. For more information about linking to
> Azure PowerShell content, see
> [Linking to other documents](/powershell/scripting/community/contributing/editorial-checklist#linking-to-other-documents).

## Parameter order

Parameters for an Azure PowerShell cmdlet should appear in the order defined by the cmdlet help. A
cmdlet can have multiple ways to provide the required parameters. When it does, follow the parameter
set for the usage you're demonstrating. An example of a cmdlet with multiple ways to invoke it is
[Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount).

## Variables

Avoid reusing variables across multiple code blocks.

The reader may complete the article steps in different sessions. Using variables across code blocks
may cause errors if they're not set correctly. If you must use the variables across steps, make it
clear that variables are reused in later steps.

## Randomize passwords for new resources

If you're creating a resource that has a password associated with it, **don't** use a hardcoded
password. Checking passwords into source control, even examples, is a security risk.

If the Azure resources in your article require a plain text password, use `Read-Host` to allow users
to define their password. The **MaskInput** parameter prevents the password from being recorded in
PowerShell's history.

```powershell
$password = Read-Host 'Enter a Password' -MaskInput
```

## Avoid naming conflicts

Some Azure resources, like Azure Container Registry and Key Vault, have resources tied to domain
names. Those resources must have a globally unique name. For that reason, use a random value as part
of names when uniqueness is required. If you don't, scripts fail to create required resources when
multiple people run them. Randomness doesn't prevent conflict but can mitigate it.

Use `Get-Random` to add a random number to a name, for example:

```powershell
$newAcrName = "myacr-$(Get-Random)"
```

## Interactive code snippets (Try It)

### When to use Try It

If Cloud Shell supports _every_ Azure PowerShell command in your article, tag your code blocks with
`azurepowershell-interactive` to add the _Try It_ button to the snippets:

````
```azurepowershell-interactive
Get-AzResourceGroup | Select-Object -Property ResourceGroupName, Location
```
````

### When NOT to use Try It

Don't use `azurepowershell-interactive` if your article includes _any_ Azure PowerShell commands
that don't work in Cloud Shell. Use `azurepowershell` only. For example, the `Install-AzAksCliTool`
cmdlet is unsupported in Cloud Shell:

```azurepowershell
Install-AzAksCliTool
```

If you mix Cloud Shell functional commands with commands that don't work in Cloud Shell, you risk
frustrating customers when only _some_ commands work. Instead, stick with the `azurepowershell`
language tag for all code blocks to help avoid confusion.

Because users are already authenticated when logging into Cloud Shell, don't use the
`azurepowershell-interactive` tag for code blocks containing only `Connect-AzAccount`. Use the
`azurepowershell` language tag instead.

## Update AzureRM to the Az PowerShell module

See [Migrate Azure PowerShell from AzureRM to Az](migrate-from-azurerm-to-az.md) for information on
how to update commands that use the AzureRM PowerShell module to the Az PowerShell module.
