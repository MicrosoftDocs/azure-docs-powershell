# Azure PowerShell documentation

This repository hosts the documentation source for the Azure PowerShell module, published on [docs.microsoft.com](https://docs.microsoft.com/powershell/azure/).

## Public contributions

We welcome public contributions to the Azure PowerShell documentation! There are two types of documentation hosted in this repository,
with different workflows:

* To submit a change for _conceptual_ documentation (content in the `docs-conceptual` directory) make a pull request against
  this repository. Keep in mind that there's conceptual documentation maintained for every major version - update all of the
  affected files!
* To submit a change for _previous versions' reference_ documentation (all documentation for AzureRM and Az 1.x), make a pull request against this
  repository. This will only update the online help available for these modules, as no old versions are rebuilt if the help is updated.
* To submit a change for the _current version's reference_ please make a pull request against
  [azure/azure-powershell](https://github.com/azure/azure-powershell). This reference is generated from the source code, and is also used in
  the command-line help.

## Microsoft Open Source Code of Conduct

This project uses [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information, see [Code of Conduct FAQs](https://opensource.microsoft.com/codeofconduct/faq/) or contact opencode@microsoft.com for further questions or comments.
