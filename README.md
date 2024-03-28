# Azure PowerShell documentation

This repository contains the documentation for Azure PowerShell module, published on
[learn.microsoft.com][ms-learn].

## Public contributions

We welcome public contributions to the Azure PowerShell documentation. There are two types of
documentation hosted in this repository, with different workflows:

- To submit a change for _conceptual_ documentation (content in the `docs-conceptual` directory),
  make a pull request against this repository. Conceptual documentation is maintained for every
  supported version, so update all the affected versions.
- To submit a change for _current versions' reference_ documentation, submit a pull request against
  this repository. This only updates the online help available for current and previous versions.
- To submit a change for _future version reference_ documentation, submit a pull request against
  [azure/azure-powershell][azps-source-repo]. The reference content for new versions of the Az
  PowerShell module is generated from the source code and is also used in the command-line help.

## Microsoft Open Source Code of Conduct

This project uses [Microsoft Open Source Code of Conduct][opensource-conduct]. For more information,
see [Code of Conduct FAQs][conduct-faq] or contact [opencode@microsoft.com][conduct-email] for
further questions or comments.

<!-- link references -->

[ms-learn]: (https://learn.microsoft.com/powershell/azure/)
[azps-source-repo]: https://github.com/azure/azure-powershell
[opensource-conduct]: https://opensource.microsoft.com/codeofconduct/
[conduct-faq]: https://opensource.microsoft.com/codeofconduct/faq/
[conduct-email]: mailto:opencode@microsoft.com
