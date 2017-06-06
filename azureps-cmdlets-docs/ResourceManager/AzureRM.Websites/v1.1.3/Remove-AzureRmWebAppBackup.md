---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmWebAppBackup

## SYNOPSIS
Removes the specified backup of a web app.

## SYNTAX

### FromResourceName
```
Remove-AzureRmWebAppBackup [-BackupId] <String> [-ResourceGroupName] <String> [-Name] <String>
 [[-Slot] <String>] [<CommonParameters>]
```

### FromWebApp
```
Remove-AzureRmWebAppBackup [-BackupId] <String> [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmWebAppBackup** cmdlet removes the specified backup of a web app that was built using the Web Apps feature of the Azure App Service.

## EXAMPLES

### Example 1: Remove the specified backup
```
PS C:\> Remove-AzureRmWebAppBackup -ResourceGroupName "Default-Web-WestUS" -Name "WebAppStandard" -BackupId "12345"
```

This command removes the "12345" backup of the web app named "WebAppStandard" that is in the "Default-Web-WestUS" resource group.

## PARAMETERS

### -BackupId
Specifies the ID of the backup to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmWebAppBackup](./Get-AzureRmWebAppBackup.md)

[Get-AzureRmWebAppBackupConfiguration](./Get-AzureRmWebAppBackupConfiguration.md)

[Get-AzureRmWebAppBackupList](./Get-AzureRmWebAppBackupList.md)
