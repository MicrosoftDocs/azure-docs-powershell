# Azure PowerShell documentation

This repository contains the official product documentation for Azure PowerShell, published on
[learn.microsoft.com][azps-docs].

## Microsoft Open Source Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct][code-of-conduct].

## Public contributions

We welcome public contributions to the Azure PowerShell documentation. There are two types of
documentation hosted in this repository, with different workflows:

- To submit a change for _conceptual_ documentation (content in the `docs-conceptual` directory),
  make a pull request against this repository. Conceptual documentation is maintained for every
  supported version, so update all the affected versions.
- To submit a change for _current versions of reference_ documentation, submit a pull request
  against this repository. This only updates the online help available for current and previous
  versions.

> NOTE: To submit a change for _future versions of reference_ documentation, submit a pull request
> against [azure/azure-powershell][azps-source-repo]. The reference content for new versions of the
> Az PowerShell module is generated from the source code and is also used in the command-line help.

Please note that before we can accept your pull request you must sign our
[Contribution License Agreement][cla]. This is a one-time requirement.

<!-- link references -->

[azps-docs]: https://learn.microsoft.com/powershell/azure/
[code-of-conduct]: CODE_OF_CONDUCT.md
[azps-source-repo]: https://github.com/azure/azure-powershell
[cla]: https://cla.microsoft.com/
