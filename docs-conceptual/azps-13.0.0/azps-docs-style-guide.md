---
description: This article provides the rules of style for writing Azure PowerShell documentation.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell docs style guide
---

# Azure PowerShell docs style guide

This article focuses on Azure PowerShell conceptual and reference content available in the following
GitHub repositories:

- [azure-docs-powershell][azps-docs-repo]
- [azure-powershell][azps-source-repo]

## Version

Unlike most Microsoft Learn documentation, the Azure PowerShell content in the
**azure-docs-powershell** repository is maintained for multiple supported versions. For details on
supported versions, see [Azure PowerShell support lifecycle][support-lifecycle].

If an article references cmdlets from a preview module, that module must be explicitly installed
unless the **AzPreview** module is already installed. This is because only generally available (GA)
modules are included with the **Az** PowerShell module.

> [!IMPORTANT]
> Don't use commands from the **AzureRM** PowerShell module in articles. **AzureRM** is deprecated.

## Prerequisites

Always place Azure service prerequisites first, followed by Azure PowerShell and Azure Cloud Shell
instructions. For example, "You must have `Microsoft.Authorization/roleAssignments/write`
permissions to complete the instructions in this tutorial" should come first.

If all commands aren't compatible with Cloud Shell, instruct the user to install the **Az**
PowerShell module locally. Include the following text in an H2 Prerequisites section.

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

Don't link to cmdlet documentation when mentioning cmdlet names in a paragraph. Instead, surround
the cmdlet name with backticks, which is styling for inline code (``). Add a references section
towards the bottom of the page. List the cmdlet names in the references section and link to their
associated reference article. For example:

```markdown
This is an example of using the `Connect-AzAccount` and `Get-AzVM` cmdlets within a
paragraph.

## References

- [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount)
- [Get-AzVM](/powershell/module/az.compute/get-azvm)
```

> [!NOTE]
> Don't format text inside the brackets of a hyperlink. For more information about linking to
> Azure PowerShell content, see
> [Linking to other documents](/powershell/scripting/community/contributing/editorial-checklist#linking-to-other-documents).

## Parameter order

Parameters for an Azure PowerShell cmdlet should appear in the order defined by the cmdlet help. A
cmdlet can have multiple ways to provide the required parameters. When it does, follow the parameter
set for the usage you're demonstrating. `Connect-AzAccount` is an example of a cmdlet with multiple
ways to invoke it.

## Variables

Avoid reusing variables across multiple code blocks.

The reader might complete the article steps in different sessions. Using variables across code
blocks might cause errors if they're not set correctly. If you must use the variables across steps,
make it clear that variables are reused in later steps.

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

[azps-docs-repo]: https://github.com/MicrosoftDocs/azure-docs-powershell
[azps-source-repo]: https://github.com/Azure/azure-powershell
[support-lifecycle]: azureps-support-lifecycle.md
