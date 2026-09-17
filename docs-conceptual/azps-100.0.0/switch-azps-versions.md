---
title: Switch between classic and preview Azure PowerShell (Preview)
description: Learn how the preview Az modules coexist with your classic Az installation and how to choose which version loads in a PowerShell session.
ms.topic: conceptual
---

# Switch between classic and preview Azure PowerShell (Preview)

The preview Az modules install side by side with your existing (classic) Az modules. Both use the
same module names (`Az`, `Az.Compute`, and so on), so a single PowerShell session can load only one
of them at a time. This article explains how to choose which version loads and how to switch between
them.

## How coexistence works

When you install the preview, its modules land in the same module path as the classic modules, just
at a different version number. The preview ships as version `0.1.0`; classic releases use higher
version numbers (for example, `15.6.0`).

| Product | Example version | Notes |
| --- | --- | --- |
| Classic Azure PowerShell | `15.6.0` | Your existing, full Az installation. |
| Preview (azclips) | `0.1.0` | The private-preview modules. |

Because both versions are available, PowerShell decides which one to load based on the version you
request. See [Install Azure PowerShell modules][01] for how the preview is installed.

## Check which versions are installed

List every installed version of the `Az` module:

```powershell
Get-Module Az -ListAvailable | Select-Object Name, Version, ModuleBase
```

The preview appears as version `0.1.0`. If you also have classic Azure PowerShell, its higher
version numbers appear in the same list.

## Load a specific version

Use `Import-Module` with a version constraint to choose which version loads in the current session.

Load the **preview**. Preview builds ship frequently (`0.1.0`, `0.1.1`, `0.1.2`, and so on), so pin
the `0.1.*` range instead of a fixed number to always load the newest preview:

```powershell
Import-Module Az -MinimumVersion 0.1.0 -MaximumVersion 0.1.9999
```

To load one exact build instead, use `-RequiredVersion` with its version number:

```powershell
Import-Module Az -RequiredVersion 0.1.0
```

Load the **classic** version (use the version number from the previous step):

```powershell
Import-Module Az -RequiredVersion 15.6.0
```

> [!NOTE]
> If you run `Import-Module Az` without a version, PowerShell loads the **highest** installed
> version. When classic Azure PowerShell is present, that means the classic modules load, not the
> preview. Pass the `0.1.*` range (or a specific `-RequiredVersion`) to load the preview.

## Confirm which version is active

Check the version of the `Az` module loaded in the current session:

```powershell
Get-Module Az | Select-Object Name, Version
```

A version in the `0.1.*` range (for example `0.1.0`) means the preview is active. A higher version
means the classic modules are active. If nothing is returned, no `Az` module is loaded yet in this
session.

## Switch between versions

**Each PowerShell session can use only one version.** Decide which version you want before you run
your first `Import-Module Az`, and start a new session to switch.

You can't switch versions inside a running session. The Az modules load binary (.NET) components,
and once those are loaded, PowerShell can't replace them with a different version. Attempting to
import the other version fails with an error such as:

```
Import-Module: Could not load file or assembly '...'. Assembly with same name is already loaded
```

`Remove-Module` doesn't help either: it removes the PowerShell module, but the loaded assemblies stay
in the process. To switch, close the current session and start a new one — for example, run `exit`
and then launch `pwsh` again. In the new session, load the version you want:

```powershell
Import-Module Az -MinimumVersion 0.1.0 -MaximumVersion 0.1.9999
```

### Optional: helper functions

To make switching feel seamless, add functions to your PowerShell profile that each start a clean
session in the version you want:

```powershell
function az-preview { pwsh -NoExit -Command 'Import-Module Az -MinimumVersion 0.1.0 -MaximumVersion 0.1.9999' }
function az-classic { pwsh -NoExit -Command 'Import-Module Az' }
```

Run `az-preview` or `az-classic` to open a fresh session with that version loaded.

For steps on adding these functions to your profile, see [How to edit a profile](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.6#how-to-edit-a-profile).

## Related content

- [Install Azure PowerShell modules][01]
- [Get started with Azure PowerShell][02]

<!-- link references -->

[01]: ./install-powershell-modules.md
[02]: ./getting-started.md
