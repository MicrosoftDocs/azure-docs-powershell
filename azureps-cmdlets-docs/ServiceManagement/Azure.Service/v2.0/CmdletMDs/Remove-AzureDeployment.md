---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureDeployment.md
schema: 2.0.0
---

# Remove-AzureDeployment

## SYNOPSIS
Deletes a deployment of a cloud service.

## SYNTAX

```
Remove-AzureDeployment [-ServiceName] <String> [-Slot] <String> [-DeleteVHD] [-Force]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDeployment** cmdlet deletes a deployment of an Azure cloud service.
To delete a deployment, first suspend it.

## EXAMPLES

### Example 1: Remove a deployment
```
PS C:\>Remove-AzureDeployment -ServiceName "ContosoService"
```

This command removes the deployment of the Azure service named ContosoService.
Because this command does not specify a slot, it removes the service from the production environment.

### Example 2: Remove a deployment and virtual hard disks
```
PS C:\>Remove-AzureDeployment -ServiceName "ContosoService" -DeleteVHD
```

This command removes the deployment of the service named ContosoService from the production environment.
The command also removes the underlying virtual hard disks.

## PARAMETERS

### -ServiceName
Specifies the name of the service for which this cmdlet deletes a deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the deployment environment from which this cmdlet deletes the deployment.
Valid values are: Staging and Production.
The default value is Production.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeleteVHD
Specifies that this cmdlet removes the deployment and the virtual hard disks (VHDs) from blob storage.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ManagementOperationContext

## NOTES

## RELATED LINKS

[Get-AzureDeployment](.\Get-AzureDeployment.md)

[Get-AzureDeploymentEvent](.\Get-AzureDeploymentEvent.md)

[Move-AzureDeployment](.\Move-AzureDeployment.md)

[New-AzureDeployment](.\New-AzureDeployment.md)

[Set-AzureDeployment](.\Set-AzureDeployment.md)

