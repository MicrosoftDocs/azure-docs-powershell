---
title: Use the Azure Az PowerShell module behind a proxy server
description: How to use the Azure Az PowerShell module behind a proxy server
ms.date: 08/09/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Use the Azure Az PowerShell module behind a proxy server

If a proxy is necessary for HTTP request, the Azure PowerShell team recommends the following proxy
configuration for different platforms:

     **Platform**       |                          **Recommended Proxy Settings**                           |                                               **Comment**
----------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------
Windows PowerShell 5.1  | System proxy settings                                                             | Do not suggest setting HTTP_PROXY/HTTPS_PROXY environment variables.
PowerShell 7 on Windows | System proxy settings                                                             | Proxy could be configured by setting both HTTP_PROXY and HTTPS_PROXY environment variables.
PowerShell 7 on MacOS   | System proxy settings                                                             | Proxy could be configured by setting both HTTP_PROXY and HTTPS_PROXY environment variables.
PowerShell 7 on Linux   | Set both HTTP_PROXY and HTTPS_PROXY environment variables, plus optional NO_PROXY | The environment variables should be set before starting powershell, otherwise they may not be respected.

The environment variables used are:

-	HTTP_PROXY: the proxy server used on HTTP requests.
-	HTTPS_PROXY: the proxy server used on HTTPS requests.
-	NO_PROXY: a comma-separated list of hostnames that should be excluded from proxying.

On systems where environment variables are case-sensitive, the variable names may be all lowercase
or all uppercase. The lowercase names are checked first.
