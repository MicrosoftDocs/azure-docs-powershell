---
title: Run Azure PowerShell in a Docker container
description: How to run Azure PowerShell in a Docker container.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/09/2018
---
# Run Azure PowerShell in a Docker container

Microsoft publishes Docker images with Azure PowerShell pre-installed. These images allow for experimenting with Azure PowerShell or running it in an isolated environment. There are images running both PowerShell Core and
PowerShell 5. 

| Environment | Docker image |
|-------------|--------------|
| PowerShell on Windows | [azuresdk/azure-powershell](https://hub.docker.com/r/azuresdk/azure-powershell/) |
| PowerShell Core on Windows | [azuresdk/azure-powershell-core:nanoserver](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |
| PowerShell Core on Linux | [azuresdk/azure-powershell-core:latest](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |

To run any of these containers, use `docker run -it $ImageName` to get an interactive terminal. For example, to run a Linux container with PowerShell Core:

```powershell
docker run -it azuresdk/azure-powershell-core:latest
```

> [!NOTE]
> To run a Windows container in Docker, your host OS must be Windows and Docker must be set to
> run Windows containers. To learn about switching between Windows and Linux environments in Docker,
> see the Docker documentation [Switch between Windows and Linux containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).

## Use a PowerShell Core container

The PowerShell Core containers come with PowerShell Core v6 and the `AzureRM.NetCore` module pre-installed. Run the [Import-Module](/powershell/module/microsoft.powershell.core/import-module) cmdlet and then sign in with your Azure account:

```powershell
Import-Module AzureRM.NetCore
Connect-AzureRmAccount
```

## Use the Windows container with PowerShell

The Windows container has the `AzureRM` module pre-installed. Run the [Import-Module](/powershell/module/microsoft.powershell.core/import-module)
cmdlet and then sign in with your Azure account:

```powershell
Import-Module AzureRM
Connect-AzureRmAccount
```
