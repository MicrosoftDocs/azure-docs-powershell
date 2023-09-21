---
description: Learn how to run a Docker container hosting Azure PowerShell. Docker gets you started quickly with an isolated environment in which to run Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023  
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: How to run Azure PowerShell in a Docker container
---

# Using Azure PowerShell in a Docker container

We publish Docker images with Azure PowerShell preinstalled. You can use Docker to run a standalone
Linux container with Azure PowerShell preinstalled. This article shows you how to use Azure
PowerShell in the Docker container.

## Finding available images

The released images require Docker 17.05 or newer. You must be able to run Docker without `sudo` or
local administrative rights. Follow Docker's official [instructions][install] to install Docker.

The release containers derive from the official distribution image, install dependencies, and
install the Azure PowerShell module.

The latest container image contains the latest version of PowerShell and the latest Azure PowerShell
modules supported with the Az PowerShell module.

You can find a complete list of Azure PowerShell Docker images on our [Docker image][az image] page.

## Using Azure PowerShell in a container

The following steps show the Docker commands required to download the image and start an interactive
PowerShell session.

# [amd64](#tab/amd64)

1. Download the latest azure-powershell image.

   ```console
   docker pull mcr.microsoft.com/azure-powershell
   ```

1. Run the azure-powershell container in interactive mode:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell pwsh
   ```

# [arm64](#tab/arm64)

1. Download the latest azure-powershell image.

   ```console
   docker pull mcr.microsoft.com/azure-powershell:mariner-2-arm64
   ```

1. Run the azure-powershell container in interactive mode:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell:mariner-2-arm64 pwsh
   ```

---

For Windows Docker hosts, you must enable Docker file sharing to allow local drives on Windows to be
shared with Linux containers. For more information, see
[Get started with Docker for Windows][file-sharing].

### Remove the image when no longer needed

The following command deletes the Docker container when you no longer need it.

# [amd64](#tab/amd64)

```console
docker rmi mcr.microsoft.com/azure-powershell
```

# [arm64](#tab/arm64)

```console
docker rmi mcr.microsoft.com/azure-powershell:mariner-2-arm64
```

---

## Next steps

To learn more about the Azure PowerShell modules and their features, see
[Get Started with Azure PowerShell](get-started-azureps.md).

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[az image]: https://hub.docker.com/_/microsoft-azure-powershell
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
