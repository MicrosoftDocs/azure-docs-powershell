---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397626
schema: 2.0.0
---

# Remove-AzureEnvironment

## SYNOPSIS
Deletes an Azure environment from Windows PowerShell

## SYNTAX

```
Remove-AzureEnvironment [-Name] <String> [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureEnvironment** cmdlet deletes an Azure environment from your roaming profile so Windows PowerShell can't find it.
This cmdlet does not delete the environment from Microsoft Azure, or change the actual environment in any way.

An Azure environment an independent deployment of Microsoft Azure, such as AzureCloud for global Azure and AzureChinaCloud for Azure operated by 21Vianet in China.
You can also create on-premises Azure environments by using Azure Pack and the WAPack cmdlets.
For more information, see Azure Packhttp://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx (http://www.microsoft.com/server-cloud/products/windows-azure-pack/default.aspx).

## EXAMPLES

### Example 1: Delete an environment
```
PS C:\>Remove-AzureEnvironment -Name ContosoEnv
```

This command deletes the ContosoEnv environment from Windows PowerShell.

### Example 2: Delete multiple environments
```
PS C:\>Get-AzureEnvironment | Where-Object EnvironmentName -like "Contoso*" | ForEach-Object {Remove-AzureEnvironment -Name $_.EnvironmentName }
```

This command deletes environments whose names begin with "Contoso" from Windows PowerShell.

## PARAMETERS

### -Name
Specifies the name of the environment to remove.
This parameter is required.
This parameter value is case-sensitive.
Wildcard characters are not permitted.

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

### -Force
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You can pipe input to this cmdlet by property name, but not by value.

## OUTPUTS

### None or System.Boolean
If you use the **PassThru** parameter, this cmdlet returns a Boolean value.
Otherwise, it does not return any output.

## NOTES

## RELATED LINKS

[Add-AzureEnvironment](.\Add-AzureEnvironment.md)

[Get-AzureEnvironment](.\Get-AzureEnvironment.md)

[Set-AzureEnvironment](.\Set-AzureEnvironment.md)

