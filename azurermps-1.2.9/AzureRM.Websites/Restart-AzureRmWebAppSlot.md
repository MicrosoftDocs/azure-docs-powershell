---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Restart-AzureRmWebAppSlot

## SYNOPSIS
Stops and then restarts a web app slot.

## SYNTAX

### S1
```
Restart-AzureRmWebAppSlot [-ResourceGroupName] <String> [-Name] <String> [-Slot] <String> [<CommonParameters>]
```

### S2
```
Restart-AzureRmWebAppSlot [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The **Restart-AzureRmWebAppSlot** cmdlet stops and then restarts a web app slot.
If the web app slot is in a stopped state, use the **Start-AzureRmWebAppSlot** cmdlet to start the web app slot.


## EXAMPLES

### Example 1: Restart a web app slot
```
PS C:\> Restart-AzureRmWebAppSlot -ResourceGroupName "Default-Web-WestUS" -Name "ContosoWebApp" -Slot "Slot001"
```

This command restarts the slot named "Slot001" for the web app named "ContosoWebApp" that is in the "Default-Web-WestUS" resource group.

## PARAMETERS

### -Name
Specifies the name of the web app.

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
Specifies the name of the resource group that contains the web app.

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

### -Slot
Specifies the name of the slot to restart.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Specifies a **WebApp** object that contains details about the web app.

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

### System.String
### Microsoft.Azure.Management.WebSites.Models.Site

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)

[Get-AzureRmWebAppSlot](./Get-AzureRmWebAppSlot.md)

[New-AzureRmWebAppSlot](./New-AzureRmWebAppSlot.md)

[Remove-AzureRmWebAppSlot](./Remove-AzureRmWebAppSlot.md)

[Set-AzureRmWebAppSlot](./Set-AzureRmWebAppSlot.md)

[Start-AzureRmWebAppSlot](./Start-AzureRmWebAppSlot.md)

[Stop-AzureRmWebAppSlot](./Stop-AzureRmWebAppSlot.md)
