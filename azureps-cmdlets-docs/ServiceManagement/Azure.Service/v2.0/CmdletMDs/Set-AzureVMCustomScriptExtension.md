---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVMCustomScriptExtension.md
schema: 2.0.0
---

# Set-AzureVMCustomScriptExtension

## SYNOPSIS
Sets information for an Azure virtual machine custom script extension.

## SYNTAX

### SetCustomScriptExtensionByContainerAndFileNames (Default)
```
Set-AzureVMCustomScriptExtension [[-ReferenceName] <String>] [[-Version] <String>] [-ContainerName] <String>
 [-FileName] <String[]> [[-StorageAccountName] <String>] [[-StorageEndpointSuffix] <String>]
 [[-StorageAccountKey] <String>] [[-Run] <String>] [[-Argument] <String>] [-ForceUpdate] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### DisableCustomScriptExtension
```
Set-AzureVMCustomScriptExtension [[-ReferenceName] <String>] [[-Version] <String>] [-Disable] [-ForceUpdate]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### UninstalleCustomScriptExtension
```
Set-AzureVMCustomScriptExtension [[-ReferenceName] <String>] [[-Version] <String>] [-Uninstall] [-ForceUpdate]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### SetCustomScriptExtensionByUriLinks
```
Set-AzureVMCustomScriptExtension [[-ReferenceName] <String>] [[-Version] <String>] [[-FileUri] <String[]>]
 [-Run] <String> [[-Argument] <String>] [-ForceUpdate] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMCustomScriptExtension** cmdlet sets information for an Azure virtual machine custom script extension.

## EXAMPLES

### Example 1: Set information for a virtual machine custom script extension
```
PS C:\>$VM = Set-AzureVMCustomScriptExtension -VM $VM -ContainerName "Container01" -FileName "script1.ps1","script2.ps1" -Run "script1.ps1" -Argument "arg1 arg2";
PS C:\> New-AzureVM -Location "West US" -ServiceName $SVC -VM $VM;
```

This command sets information for a virtual machine custom script extension.

### Example 2: Set information for a virtual machine custom script extension using a file path
```
PS C:\>Set-AzureVMCustomScriptExtension -VM $VM -FileUri "http://www.blob.core.contoso.net/bar/script1.ps1","http://www.blob.core.contoso.net/baz/script2.ps1" -Run "script1.ps1" -Argument "arg1 arg2";
PS C:\> Update-AzureVM -ServiceName $SVC -Name $Name -VM VM;
```

This command sets information for a virtual machine custom script extension using multiple file URLs.

## PARAMETERS

### -ReferenceName
Specifies the reference name for the extension.

This parameter is a user-defined string that can be used to refer to an extension.
It is specified when the extension is added to the virtual machine for the first time.
For subsequent updates, you need to specify the previously used reference name while updating the extension.
The *ReferenceName* assigned to an extension is returned using the Get-AzureVM cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the custom script extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerName
Specifies the container name within the storage account.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileName
Specifies a string array that contains the names of the blob files in the specified container.

```yaml
Type: String[]
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the storage account name in the current subscription.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEndpointSuffix
Specifies the storage service endpoint.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountKey
Specifies the storage account key

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Run
Specifies the command this cmdlet runs by the extension on the virtual machine.
Only "powershell.exe" is supported.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames
Aliases: RunFile, Command

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByUriLinks
Aliases: RunFile, Command

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Argument
Specifies a string that supplies an argument that this cmdlet runs on the virtual machine.

```yaml
Type: String
Parameter Sets: SetCustomScriptExtensionByContainerAndFileNames, SetCustomScriptExtensionByUriLinks
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceUpdate
Indicates that this cmdlet re-apply a configuration to an extension when the configuration has not been updated.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Disable
Indicates that this cmdlet disables the extension state.

```yaml
Type: SwitchParameter
Parameter Sets: DisableCustomScriptExtension
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Uninstall
Indicates that this cmdlet uninstalls the custom script extension from the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: UninstalleCustomScriptExtension
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileUri
Specifies a string array that contains the URLs of the blob files.

```yaml
Type: String[]
Parameter Sets: SetCustomScriptExtensionByUriLinks
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMCustomScriptExtension](.\Get-AzureVMCustomScriptExtension.md)

[Remove-AzureVMCustomScriptExtension](.\Remove-AzureVMCustomScriptExtension.md)

[Get-AzureVM](.\Get-AzureVM.md)

