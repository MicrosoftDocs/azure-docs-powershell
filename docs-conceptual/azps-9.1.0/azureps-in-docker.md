---
description: How to use Azure PowerShell that is preinstalled in a Docker image.
ms.custom: devx-track-azurepowershell
ms.date: 11/01/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Using Azure PowerShell in Docker
---

# Using Azure PowerShell in Docker

We are publishing Docker images with Azure PowerShell preinstalled. This article shows you how to
get started using Azure PowerShell in the Docker container.

## Finding available images

The released images require Docker 17.05 or newer. It is also expected that you are able to run
Docker without `sudo` or local administrative rights. Please follow Docker's official
[instructions][install] to install `docker` correctly.

The latest container image contains the latest version of PowerShell and the latest Azure PowerShell
modules supported with the Az module.

For each new release of the Az module we are releasing an image for the following operating systems:

- Ubuntu 20.04 (default)
- Debian 9
- CentOS 7

A full list of available images can be found on our [Docker image][az image] page.

## Using Azure PowerShell in a container

The following steps show the Docker commands required to download the image and start an interactive
PowerShell session.

1. Download the latest azure-powershell image.

   ```console
   docker pull mcr.microsoft.com/azure-powershell
   ```

1. Run the azure-powershell container in interactive mode:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell pwsh
   ```

For Windows Docker hosts, you must enable Docker file sharing to allow local drives on Windows to be
shared with Linux containers. For more information see
[Get started with Docker for Windows][file-sharing].

### Remove the image when no longer needed

The following command is used to delete the Docker container when you no longer need it.

```console
docker rmi mcr.microsoft.com/azure-powershell
```

## Next steps

To learn more about the Azure PowerShell modules and their features, see
[Get Started with Azure PowerShell](get-started-azureps.md).

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[powershell image]: https://hub.docker.com/_/microsoft-powershell
[az image]: https://hub.docker.com/_/microsoft-azure-powershell
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
