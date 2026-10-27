---
title: Get started with Azure PowerShell (preview)
description: Learn the core concepts, supported environments, authentication model, current limitations, and coexistence guidance for Azure PowerShell during the preview.
ms.date: 10/27/2026
ai-usage: ai-assisted
---

# Get started with Azure PowerShell (preview)

This article introduces the Azure PowerShell preview and explains its core concepts, supported
environments, and current limitations.

## What is Azure PowerShell?

The Azure PowerShell preview is an AI-enhanced command-line experience for Azure that helps you work more
efficiently by reducing the complexity of Azure PowerShell commands.

Rather than replacing existing tools, the Azure PowerShell preview builds on them by providing intelligent
assistance while continuing to use the same Azure management APIs and authentication model.

## Core concepts

The Azure PowerShell preview uses the following core concepts:

- **Profile-based authentication**: Save named sign-in contexts for different accounts and subscriptions.
- **AI-assisted workflows**: AI helps explain errors, recommend next steps, and improve
  productivity.
- **Cross-platform**: Runs on operating systems supported by PowerShell 7.6 or later.
- **Side-by-side installation**: Install the preview alongside existing Azure PowerShell and Azure CLI
  installations.

## Authentication

Sign in to the Azure PowerShell preview with `Connect-AzAccount`.

Azure PowerShell and Azure CLI don't share authenticated sessions during the preview. If you use
both tools, sign in separately to each: use `Connect-AzAccount` for Azure PowerShell and `az login`
for Azure CLI.

For the best experience, use interactive user authentication.

## Current limitations

The preview primarily supports interactive command-line use. Some automation scenarios and
noninteractive authentication methods aren't yet supported.

Authentication support is currently limited to interactive user sign-in.

The following authentication methods are currently **not supported**:

- Resource Owner Password Credentials (ROPC)
- Service principals
- Managed identities

Other preview limitations include:

- Not all Azure PowerShell and Azure CLI scenarios are available.
- Feature availability may change between preview releases.

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

- Any operating system supported by PowerShell 7.6 or later

### Supported shells

- PowerShell 7.6 or later

### Unsupported environments

The following environments aren't supported:

- Windows PowerShell 5.1
- Windows PowerShell Integrated Scripting Environment (ISE)

## Logging issues and providing feedback

To share feedback from the command line, run `Invoke-AzSurvey`.

If you encounter an issue:

1. Verify that you're using a supported operating system and PowerShell 7.6 or later.
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

Before sharing commands, logs, or output, remove credentials, access tokens, and sensitive information.

<!-- link references -->

[01]: https://github.com/Azure/azclips/issues
