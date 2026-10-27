---
title: "Tutorial: Store and retrieve application data with Azure PowerShell (preview)"
description: "Plan a blob and file-share round trip, compare downloaded data, and clean up test storage with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Store and retrieve application data with Azure PowerShell (preview)

In this tutorial, you plan a blob and file-share round trip, compare downloaded data, and clean up test storage with Azure PowerShell preview.

In this tutorial, you:

> [!div class="checklist"]
> - Create the storage environment
> - Upload data
> - Retrieve data
> - Share a file (optional)
> - Clean up

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

> [!IMPORTANT]
> This walkthrough is incomplete. The source doesn't yet provide the data-plane commands or authentication steps for the blob and file-share operations. Don't run the resource-creation steps until those operations are available and validated.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- Permission to upload and download data in the test storage account.

Use only synthetic test data.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-data-$run"
$account = "clips$([guid]::NewGuid().ToString('N').Substring(0, 18))"
$container = "data-$run"
$share = "files-$run"
$temp = [IO.Path]::GetTempPath()
$source = Join-Path $temp "$rg-source.txt"
$blobDownload = Join-Path $temp "$rg-blob.txt"
$fileDownload = Join-Path $temp "$rg-file.txt"
```

## Create the storage environment

```powershell
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
New-AzStorageAccount -ResourceGroupName $rg -Name $account -Location $location -SkuName Standard_LRS -Kind StorageV2
Get-AzStorageAccount -ResourceGroupName $rg -Name $account
```

Create a private blob container named `$container` in `$account`: **Pending engineering confirmation: blob container create command.**

## Upload data

```powershell
Set-Content -LiteralPath $source -Value "AzCLIPS data round trip $run" -NoNewline
```

- Upload `$source` as the blob `payload.txt`: **Pending engineering confirmation: blob upload command.**
- List the blobs in `$container`: **Pending engineering confirmation: blob list command.**

## Retrieve data

- Download `payload.txt` to `$blobDownload`: **Pending engineering confirmation: blob download command.**

```powershell
if ((Get-FileHash -LiteralPath $source).Hash -ne (Get-FileHash -LiteralPath $blobDownload).Hash) { throw 'Blob content mismatch.' }
```

## Share a file (optional)

- Create the file share `$share` in `$account`: **Pending engineering confirmation: file share create command.**
- Upload `$source` to the share: **Pending engineering confirmation: file upload command.**
- List the files in the share: **Pending engineering confirmation: file list command.**
- Download the file to `$fileDownload`: **Pending engineering confirmation: file download command.**

```powershell
if ((Get-FileHash -LiteralPath $source).Hash -ne (Get-FileHash -LiteralPath $fileDownload).Hash) { throw 'File-share content mismatch.' }
```

## Clean up resources

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
Remove-Item -LiteralPath $source, $blobDownload, $fileDownload -ErrorAction SilentlyContinue
```

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Find identities and register a Microsoft Entra application](how-to-entra-applications.md).
