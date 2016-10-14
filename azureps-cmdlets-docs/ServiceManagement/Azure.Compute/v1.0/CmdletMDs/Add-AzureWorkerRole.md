---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureWorkerRole

## SYNOPSIS
Creates required files and configuration (sometimes referred to as scaffolding) for a custom worker role.

## SYNTAX

```
Add-AzureWorkerRole [[-TemplateFolder] <String>] [[-Name] <String>] [[-Instances] <Int32>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Add-AzureWorkerRole** cmdlet creates required files and configuration (sometimes referred to as scaffolding) for a custom worker role.

## EXAMPLES

### 1: Create a single instance worker role
```
PS C:\>Add-AzureWorkerRole -Name MyWorkerRole
```

This example adds scaffolding for a single worker role named MyWorkerRole to the current application.

### 2: Create a multiple instance worker role
```
PS C:\>Add-AzureWorkerRole MyWorkerRole -I 2
```

This example adds scaffolding for a new worker role named MyWorkerRole to the current application, with a role instance count of 2.

### 3: Create worker role with custom scaffolding
```
PS C:\>Add-AzureWorkerRole MyWorkerRole -TemplateFoldr .\MyWorkerRoleTemplate
```

This example creates a worker role with custom scaffolding.

## PARAMETERS

### -Name
Specifies the name of the worker role.
This value determines the folder name that contains the scaffolding for the custom application that will be hosted in the worker role.
The default is WorkerRolenumber, where number is the number of worker roles in the service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instances
Specifies the number of role instances for this worker role.
The default is 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFolder
Specifies the scaffolding template folder to be used to create the worker role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureWebRole](.\Add-AzureWebRole.md)

[New-AzureRoleTemplate](.\New-AzureRoleTemplate.md)

