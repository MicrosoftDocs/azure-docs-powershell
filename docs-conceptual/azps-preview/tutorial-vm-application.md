---
title: "Tutorial: Deploy and manage a virtual machine application with Azure PowerShell (preview)"
description: "Deploy a web application on a virtual machine, verify a stop and start cycle, and clean up with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Deploy and manage a virtual machine application with Azure PowerShell (preview)

In this tutorial, you deploy a small web application on an Azure virtual machine (VM), verify that it works, manage the VM with Azure PowerShell preview, and clean up when you're finished.

By the end of this tutorial, the application serves a page, keeps serving it after a VM stop and start cycle, and every resource that you created for the tutorial is removed.

In this tutorial, you:

> [!div class="checklist"]
> - Prepare the environment
> - Deploy the virtual machine
> - Run the application
> - Operate the virtual machine
> - Clean up

> [!IMPORTANT]
> The SSH-key-based VM creation command still requires engineering confirmation. Don't continue with this walkthrough until that command is available and validated.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- OpenSSH tools (`ssh` and `ssh-keygen`).
- An existing network security group (NSG) in the VM's region that allows SSH (port 22) and HTTP (port 80) only from your IP address, and outbound access for Ubuntu packages.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

Verify the SSH host fingerprint when prompted. Don't disable host-key checking.

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-app-$run"
$vm = "app-$run"
$pip = "$vm-pip"
$admin = 'azadmin'
$key = Join-Path ([IO.Path]::GetTempPath()) "$vm-key"
$psVm = @{ SubscriptionId = $sub; ResourceGroupName = $rg; Name = $vm }
$page = 'AzCLIPS scenario 2 is running'
```

## Prepare the environment

```powershell
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
New-AzPublicIpAddress -SubscriptionId $sub -ResourceGroupName $rg -Name $pip -Location $location -Sku Standard -AllocationMethod Static -IpAddressVersion IPv4
```

The first command returns the new resource group with a provisioning state of `Succeeded`. The second command returns the public IP address resource. Because the allocation method is static, the address stays the same when you stop, deallocate, and start the VM later in this tutorial.

## Deploy the virtual machine

```powershell
ssh-keygen -t ed25519 -f $key -C "azclips-$run"
```

`ssh-keygen` creates a private key file and a matching `.pub` public key file in your temporary folder.

Create the Ubuntu VM with SSH-key authentication, the public IP and your NSG: **Pending engineering confirmation: New-AzVM command using SSH-key authentication.**

```powershell
Get-AzVM @psVm
```

The output shows the VM with a provisioning state of `Succeeded`.

## Run the application

```powershell
$ip = (Get-AzPublicIpAddress -SubscriptionId $sub -ResourceGroupName $rg -Name $pip).Properties.IpAddress
ssh -i $key "$admin@$ip" "sudo apt-get update && sudo apt-get install -y nginx && printf '%s\n' '$page' | sudo tee /var/www/html/index.html && sudo systemctl enable --now nginx"
$response = Invoke-WebRequest -Uri "http://$ip" -TimeoutSec 30
if ($response.Content.Trim() -ne $page) { throw 'Application verification failed.' }
```

The SSH command installs nginx and writes the test page. If the page that the VM returns matches the expected text, the check produces no output. Otherwise, it stops with `Application verification failed.`

## Operate the virtual machine

```powershell
Stop-AzVM @psVm -StayProvisioned -Force
Start-AzVM @psVm
$response = Invoke-WebRequest -Uri "http://$ip" -TimeoutSec 30
if ($response.Content.Trim() -ne $page) { throw 'Application verification failed.' }
```

`Stop-AzVM` and `Start-AzVM` wait for the operation to finish and don't return output when they succeed. `-StayProvisioned` powers off the VM but keeps its compute resources allocated. Allow up to five minutes after each start for the page to return. The application is unavailable while the VM is stopped. The check produces no output when the page matches.

Optionally, deallocate the VM, start it, and then repeat the check. Without `-StayProvisioned`, `Stop-AzVM` deallocates the VM, which releases its compute resources so that they're no longer billed.

```powershell
Stop-AzVM @psVm -Force
Start-AzVM @psVm
$response = Invoke-WebRequest -Uri "http://$ip" -TimeoutSec 30
if ($response.Content.Trim() -ne $page) { throw 'Application verification failed.' }
```

## Clean up resources

```powershell
Remove-AzVM @psVm -Force
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
Remove-Item -LiteralPath $key, "$key.pub"
```

`Remove-AzResourceGroup` deletes the resource group and everything in it, including the VM's disks and network interface, and returns `True` when the deletion completes. The `Get-AzResourceGroup` command then returns no output, which confirms that the group is gone.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Access a Key Vault secret with a managed identity](tutorial-managed-identity.md).
