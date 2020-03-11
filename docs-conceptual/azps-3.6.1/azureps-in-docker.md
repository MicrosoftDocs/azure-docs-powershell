---
title: Using Azure PowerShell in Docker
description: How to use Azure PowerShell that is preinstalled in a Docker image.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/10/2020
---

# Using Azure PowerShell in Docker

We are publishing Docker images with Azure PowerShell preinstalled. This article shows you how to
get started using Azure PowerShell in the Docker container.

## Finding available images

The released images require Docker 17.05 or newer. It is also expected that you are able to run
Docker without `sudo` or local administrative rights. Please follow Docker's official
[instructions][install] to install `docker` correctly.

The released containers are built from the official PowerShell containers, then the Az module added
as a layer.

The latest stable image includes:

- Ubuntu 18.04
- PowerShell version 6.2.4
- Azure PowerShell most current Az module

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

### Run the azure-powershell container interactively using host authentication

If you have Azure PowerShell already installed on the system hosting Docker, you may have cached
Azure credentials. These credentials can be used in the PowerShell session running in the Docker
container.

By default, the cached credentials are in `$HOME/.Azure` directory on your host. The Docker service
must have access to this location to access the credentials. The following command starts the
container with the credential cache mounted and starts an interactive PowerShell session.

```console
docker run -it -v ~/.Azure/AzureRmContext.json:/root/.Azure/AzureRmContext.json -v ~/.Azure/TokenCache.dat:/root/.Azure/TokenCache.dat mcr.microsoft.com/azure-powershell pwsh
```

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