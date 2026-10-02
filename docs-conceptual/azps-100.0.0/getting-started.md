---
title: Get started with Azure PowerShell (Preview)
description: Learn the core concepts, supported environments, authentication model, current limitations, and coexistence guidance for Azure PowerShell during the preview.
---

# Get started with Azure PowerShell (Preview)

This article introduces the core concepts of Azure PowerShell and explains what you need to know
before you begin using the preview.

## What is Azure PowerShell?

Azure PowerShell is an AI-enhanced command-line experience for Azure that helps you work more
efficiently by reducing the complexity of Azure PowerShell commands.

Rather than replacing existing tools, Azure PowerShell builds on them by providing intelligent
assistance while continuing to use the same Azure management APIs and authentication model.

## Core concepts

Azure PowerShell is designed around a few key concepts:

- **Shared authentication** - Azure PowerShell and Azure CLI share a common sign-in experience.
- **AI-assisted workflows** - AI helps explain errors, recommend next steps, and improve
  productivity.
- **Cross-platform** - Runs anywhere PowerShell 7 is supported.
- **Side-by-side installation** - Can be installed alongside existing Azure PowerShell and Azure CLI
  installations.

## Authentication

Azure PowerShell uses a shared authentication experience across Azure PowerShell and Azure CLI.

After you sign in, your authenticated session is available to both products. You don't need to sign
in separately when switching between Azure PowerShell and Azure CLI.

For the best experience, use interactive user authentication.

## Current limitations

The preview focuses on interactive user scenarios. Some authentication methods aren't yet
supported.

The following authentication methods are currently **not supported**:

- Resource Owner Password Credentials (ROPC)
- Service principals
- Managed identities

Additional authentication scenarios may be added in future releases.

## Coexistence with Azure PowerShell and Azure CLI

Azure PowerShell preview is designed to coexist with existing Azure PowerShell and Azure CLI
installations.

Installing Azure PowerShell preview doesn't replace your existing version. You can continue
using Azure PowerShell and Azure CLI exactly as you do today while evaluating Azure PowerShell
preview.

This allows you to:

- Gradually evaluate Azure PowerShell preview
- Compare workflows
- Continue using existing scripts and automation
- Roll back to your existing workflow at any time

## Supported environments

Azure PowerShell preview supports modern, cross-platform environments.

### Supported operating systems

- Any operating system PowerShell 7 is supported on

### Supported shells

- PowerShell 7 or later

### Unsupported environments

The following environments aren't supported:

- Windows PowerShell 5.1
- Windows PowerShell Integrated Scripting Environment (ISE)

## Automation support

The preview is primarily intended for interactive command-line use.

Some automation scenarios and non-interactive authentication methods aren't yet supported. For the
latest information, see the current limitations section of this article.

## Logging issues and providing feedback

Your feedback is essential during the preview.

If you encounter an issue:

1. Verify that you're using a supported operating system and PowerShell 7 or higher.
1. Reproduce the issue, if possible.
1. Collect any relevant error messages or command output.
1. Open an issue in [the AzCLIPS GitHub repository][01].

When reporting an issue, include:

- Operating system
- PowerShell version
- Azure PowerShell preview version
- Azure PowerShell or Azure CLI version, if applicable
- Steps to reproduce the problem
- Expected behavior
- Actual behavior
- Any relevant error messages

## Known preview limitations

During the preview, you should expect some limitations:

- Not all Azure PowerShell and Azure CLI scenarios are available.
- Authentication support is currently limited to interactive user sign-in.
- Feature availability may change between preview releases.

<!-- link references -->

[01]: https://github.com/Azure/azclips/issues
