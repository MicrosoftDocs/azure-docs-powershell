---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmWebAppBackupList

## SYNOPSIS
Gets a list of the backups of a web app.

## SYNTAX

### FromResourceName
```
Get-AzureRmWebAppBackupList [-ResourceGroupName] <String> [-Name] <String> [[-Slot] <String>]
 [<CommonParameters>]
```

### FromWebApp
```
Get-AzureRmWebAppBackupList [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmWebAppBackupList** cmdlet gets a list of the backups of a web app that was built using the Web Apps feature of the Azure App Service.

## EXAMPLES

### Example 1: Get a list of the backups of a web app in the specified resource group
```
PS C:\> Get-AzureRmWebAppBackupList -ResourceGroupName "Contoso" -Name "WebAppStandard"
```

This command gets a list of the backups of a web app named "WebAppStandard" in the "Contoso" resource group.

## PARAMETERS

### -Name
Specifies the name of the web app.

```yaml
Type: String
Parameter Sets: FromResourceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the web app.

```yaml
Type: String
Parameter Sets: FromResourceName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the name of the slot to which the web app is deployed.

```yaml
Type: String
Parameter Sets: FromResourceName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WebApp
Specifies a **WebApp** object that contains details about the web app.

```yaml
Type: Site
Parameter Sets: FromWebApp
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-AzureRmWebAppBackup](./Get-AzureRmWebAppBackup.md)

[Get-AzureRmWebAppBackupConfiguration](./Get-AzureRmWebAppBackupConfiguration.md)

[New-AzureRmWebAppBackup](./New-AzureRmWebAppBackup.md)
