---
title: Other ways to install and run Azure PowerShell
description: How to install Azure PowerShell without PowerShellGet, or run in a Docker container.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/20/2018
---

## Run in a Docker container

We maintain a set of Docker images preconfigured with Azure PowerShell. There are two types of containers available: Those running traditional
PowerShell on Windows, and a container running PowerShell Core on either Windows or Linux.

| Environment | Docker image |
|-------------|--------------|
| PowerShell on Windows | [azuresdk/azure-powershell](https://hub.docker.com/r/azuresdk/azure-powershell/) |
| PowerShell Core on Windows | [azuresdk/azure-powershell-core:nanoserver](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |
| PowerShell Core on Linux | [azuresdk/azure-powershell-core:latest](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |

To run any of these containers, you use `docker run -it $ImageName` to get an interactive terminal. For example, to run the PowerShell Core on Linux container,
use:

```powershell
docker run -it azuresdk/azure-powershell-core:latest
```

> [!NOTE]
> To run a Windows container in Docker, your host OS must be Windows and Docker must be set to
> run Windows containers. To learn about switching between Windows and Linux environments in Docker,
> see the Docker documentation [Switch between Windows and Linux containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).
