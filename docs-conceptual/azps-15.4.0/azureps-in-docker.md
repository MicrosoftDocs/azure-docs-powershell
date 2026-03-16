---
title: Run Azure PowerShell in a Docker container
description: Learn how to run Azure PowerShell in a Docker container using official Microsoft images. Quickly set up and manage Azure resources in an isolated environment.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
---

# Run Azure PowerShell in a Docker container

We publish Docker images with Azure PowerShell preinstalled. You can use Docker to run a standalone
Linux container with Azure PowerShell preinstalled. This article shows you how to use Azure
PowerShell in a Docker container.

## Finding available images

The released images require Docker 17.05 or newer. You must be able to run Docker without `sudo` or
local administrative rights. Follow Docker's official [instructions][install] to install Docker.

The release containers derive from the official distribution image, install dependencies, and
install the Azure PowerShell module.

The latest container image contains the latest version of PowerShell and the latest Azure PowerShell
modules supported with the Az PowerShell module.

You can find a complete list of Azure PowerShell Docker images on our [Docker image][az-image] page.

> [!IMPORTANT]
> These images are built from official operating system (OS) images provided by the OS distributor.
> These images might not have the latest security updates. Microsoft recommends that you update the
> OS packages to the latest version to ensure the latest security updates are applied.

## Using Azure PowerShell in a container

The following steps outline the Docker commands necessary to download the image and start an
interactive PowerShell session.

# [amd64](#tab/amd64)

1. Download the latest azure-powershell image.

   ```console
   docker pull mcr.microsoft.com/azure-powershell:azurelinux-3.0
   ```

1. Run the azure-powershell container in interactive mode:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell:azurelinux-3.0 pwsh
   ```

# [arm64](#tab/arm64)

1. Download the latest azure-powershell image.

   ```console
   docker pull mcr.microsoft.com/azure-powershell:azurelinux-3.0-arm64
   ```

1. Run the azure-powershell container in interactive mode:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell:azurelinux-3.0-arm64 pwsh
   ```

---

For Windows Docker hosts, you must enable Docker file sharing to allow local drives on Windows to be
shared with Linux containers. For more information, see
[Get started with Docker for Windows][file-sharing].

### Remove the image when no longer needed

The following command deletes the Docker container when you no longer need it.

# [amd64](#tab/amd64)

```console
docker rmi mcr.microsoft.com/azure-powershell:azurelinux-3.0
```

# [arm64](#tab/arm64)

```console
docker rmi mcr.microsoft.com/azure-powershell:azurelinux-3.0-arm64
```

---

## Next steps

To learn more about the Azure PowerShell modules and their features, see
[Get Started with Azure PowerShell](get-started-azureps.md).

<!-- link references -->

[install]: https://docs.docker.com/engine/installation/
[az-image]: https://aka.ms/azps-docker-images
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
