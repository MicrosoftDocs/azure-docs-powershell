---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.WebSites
ms.assetid: 297071E5-FC06-4493-BCC2-37D4929E4025
online version: https://learn.microsoft.com/en-us/powershell/module/Az.websites/restart-Azwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Websites/Websites/help/Restart-AzWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Websites/Websites/help/Restart-AzWebApp.md
---

# Restart-AzWebApp

## SYNOPSIS
Restarts an Azure Web App.

## SYNTAX

### S1
```
Restart-AzWebApp [-ResourceGroupName] <String> [-Name] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S2
```
Restart-AzWebApp [-WebApp] <Site> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-AzWebApp** cmdlet stops and then starts an Azure Web App.
If the Web App is in a stopped state, use the Start-AzWebApp cmdlet.

## EXAMPLES

### Example 1: Restart a Web App
```
PS C:\>Restart-AzWebApp -ResourceGroupName "Default-Web-WestUS" -Name "ContosoSite"
```

This command stops the Azure Web App named ContosoSite that belongs to the resource group named Default-Web-WestUS and then restarts it.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
WebApp Name

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Resource Group Name

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
WebApp Object

```yaml
Type: Site
Parameter Sets: S2
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Site
Parameter 'WebApp' accepts value of type 'Site' from the pipeline

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzWebApp](./Get-AzWebApp.md)

[New-AzWebApp](./New-AzWebApp.md)

[Remove-AzWebApp](./Remove-AzWebApp.md)

[Start-AzWebApp](./Start-AzWebApp.md)

[Stop-AzWebApp](./Stop-AzWebApp.md)


