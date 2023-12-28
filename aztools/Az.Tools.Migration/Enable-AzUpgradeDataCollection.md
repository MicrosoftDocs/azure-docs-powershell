---
external help file: Az.Tools.Migration-help.xml
Module Name: az.tools.migration
online version:
schema: 2.0.0
original_content_git_url: https://github.com/Azure/azure-powershell-migration/blob/main/powershell-module/help/Enable-AzUpgradeDataCollection.md
---

# Enable-AzUpgradeDataCollection

## SYNOPSIS
Enables the setting that allows** Az.Tools.Migration** to send usage metrics to Microsoft.

## SYNTAX

```
Enable-AzUpgradeDataCollection [<CommonParameters>]
```

## DESCRIPTION

Enables the setting that allows **Az.Tools.Migration** to send usage metrics to Microsoft. Usage
metrics are opted-in by default. To disable usage metrics, run the
`Disabled-AzUpgradeDataCollection` cmdlet. This setting is scoped to the user profile and persists
between PowerShell sessions.

## EXAMPLES

### EXAMPLE 1

Enables the metrics collection for **Az.Tools.Migration**.

```powershell
Enable-AzUpgradeDataCollection
```

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
