---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/az.cdn/import-azcdnendpointcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Import-AzCdnEndpointContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Import-AzCdnEndpointContent.md
---

# Import-AzCdnEndpointContent

## SYNOPSIS
Pre-loads a content to CDN.
Available for Verizon Profiles.

## SYNTAX

### LoadExpanded (Default)
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -ContentPath <String[]> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LoadViaJsonString
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -JsonString <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LoadViaJsonFilePath
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -JsonFilePath <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LoadViaIdentityProfileExpanded
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileInputObject <ICdnIdentity> -ContentPath <String[]>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LoadViaIdentityProfile
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileInputObject <ICdnIdentity>
 -ContentFilePath <ILoadParameters> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Load
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -ContentFilePath <ILoadParameters> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LoadViaIdentityExpanded
```
Import-AzCdnEndpointContent -InputObject <ICdnIdentity> -ContentPath <String[]> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LoadViaIdentity
```
Import-AzCdnEndpointContent -InputObject <ICdnIdentity> -ContentFilePath <ILoadParameters>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Pre-loads a content to CDN.
Available for Verizon Profiles.

## EXAMPLES

### Example 1: Import content of an AzureCDN Endpoint under the AzureCDN profile
```powershell
Import-AzCdnEndpointContent -ResourceGroupName testps-rg-verizon -ProfileName verzioncdn001 -EndpointName verzionendptest001 -ContentPath @("/movies/hello","/pictures/pic1.jpg")
```

Import content of an AzureCDN Endpoint under the AzureCDN profile, only some skus support this action

### Example 2: Import content of an AzureCDN Endpoint under the AzureCDN profile using contentFilePath parameter
```powershell
$contentPath = @("/movies/amazing.mp4","/pictures/pic1.jpg")
$contentFilePath = New-AzCdnLoadParametersObject -ContentPath $contentPath
Import-AzCdnEndpointContent -ResourceGroupName testps-rg-verizon -ProfileName verzioncdn001 -EndpointName verzionendptest001 -ContentFilePath $contentFilePath
```

Import content of an AzureCDN Endpoint under the AzureCDN profile, only some skus support this action using contentFilePath parameter

## PARAMETERS

### -AsJob
Run the command as a job

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentFilePath
Parameters required for content load.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ILoadParameters
Parameter Sets: LoadViaIdentityProfile, Load, LoadViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ContentPath
The path to the content to be loaded.
Path should be a relative file URL of the origin.

```yaml
Type: System.String[]
Parameter Sets: LoadExpanded, LoadViaIdentityProfileExpanded, LoadViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Name of the endpoint under the profile which is unique globally.

```yaml
Type: System.String
Parameter Sets: LoadExpanded, LoadViaJsonString, LoadViaJsonFilePath, LoadViaIdentityProfileExpanded, LoadViaIdentityProfile, Load
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: LoadViaIdentityExpanded, LoadViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Load operation

```yaml
Type: System.String
Parameter Sets: LoadViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Load operation

```yaml
Type: System.String
Parameter Sets: LoadViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns true when the command succeeds

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileInputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: LoadViaIdentityProfileExpanded, LoadViaIdentityProfile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProfileName
Name of the CDN profile which is unique within the resource group.

```yaml
Type: System.String
Parameter Sets: LoadExpanded, LoadViaJsonString, LoadViaJsonFilePath, Load
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the Resource group within the Azure subscription.

```yaml
Type: System.String
Parameter Sets: LoadExpanded, LoadViaJsonString, LoadViaJsonFilePath, Load
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Azure Subscription ID.

```yaml
Type: System.String
Parameter Sets: LoadExpanded, LoadViaJsonString, LoadViaJsonFilePath, Load
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ILoadParameters

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
