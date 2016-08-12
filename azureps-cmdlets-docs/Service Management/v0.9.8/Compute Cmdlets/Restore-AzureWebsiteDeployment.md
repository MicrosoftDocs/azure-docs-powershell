---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Restore-AzureWebsiteDeployment
## SYNOPSIS
Redeploys a previous deployment of a website in Azure.

## SYNTAX

```
Restore-AzureWebsiteDeployment [[-Name] <String>] [[-CommitId] <String>] [-Force] [-Slot <String>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Restore-AzureWebsiteDeployment cmdlet redeploys a previous deployment of a website in Azure.
This process replaces the current deployment with the selected deployment.

## EXAMPLES

### Example 1: Redeploy a site
```
PS C:\>Restore-AzureWebsiteDeployment -Name "ContosoSite" -CommitId "f876543210"
```

This command redeploys the deployment that has the ID f876543210 for the website named ContosoSite.

## PARAMETERS

### -CommitId
Specifies the identifier of the deployment to redeploy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
If enabled, redeploys the previous deployment without prompting for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the website to redeploy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the slot name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

