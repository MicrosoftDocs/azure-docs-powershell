---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureNodeWorkerRole

## SYNOPSIS
Creates the required files and folders for a Node.js application to be hosted in the cloud via node.exe

## SYNTAX

```
Add-AzureNodeWorkerRole [[-Name] <String>] [[-Instances] <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Add-AzureNodeWorkerRole** cmdlet creates the required files and folders (sometimes referred to as scaffolding) for a Node.js application to be hosted in the cloud via node.exe.

## EXAMPLES

### 1: Single instance worker role
```
PS C:\>Add-AzureWorkerRole MyWorkerRole
```

This example adds scaffolding for a single worker role named **MyWorkerRole** to the current application.

### 2: Multiple instance worker role
```
PS C:\>Add-AzureNodeWorkerRole MyWorkerRole -I 2
```

This example adds scaffolding for a single worker role named **MyWorkerRole** to the current application, with a role instance count of 2.

## PARAMETERS

### -Name
Specifies the name of the worker role.
The value determines the folder name that contains the scaffolding for the node.js service hosted in the worker role.
Default is WorkerRole1.

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
Default is 1.

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

[Add-AzureNodeWebRole](.\Add-AzureNodeWebRole.md)

[New-AzureServiceProject](.\New-AzureServiceProject.md)

