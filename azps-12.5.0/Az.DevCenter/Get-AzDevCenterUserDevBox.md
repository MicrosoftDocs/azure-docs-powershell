---
external help file: Az.DevCenter-help.xml
Module Name: Az.DevCenter
online version: https://learn.microsoft.com/powershell/module/az.devcenter/get-azdevcenteruserdevbox
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevCenter/DevCenter/help/Get-AzDevCenterUserDevBox.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevCenter/DevCenter/help/Get-AzDevCenterUserDevBox.md
---

# Get-AzDevCenterUserDevBox

## SYNOPSIS
Gets a Dev Box

## SYNTAX

### List (Default)
```
Get-AzDevCenterUserDevBox -Endpoint <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Get
```
Get-AzDevCenterUserDevBox -Endpoint <String> -ProjectName <String> -UserId <String> -Name <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDevCenterUserDevBox -Endpoint <String> -InputObject <IDevCenterdataIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### List1
```
Get-AzDevCenterUserDevBox -Endpoint <String> -UserId <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### List2
```
Get-AzDevCenterUserDevBox -Endpoint <String> -ProjectName <String> -UserId <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentityByDevCenter
```
Get-AzDevCenterUserDevBox -DevCenterName <String> -InputObject <IDevCenterdataIdentity>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListByDevCenter
```
Get-AzDevCenterUserDevBox -DevCenterName <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### List2ByDevCenter
```
Get-AzDevCenterUserDevBox -DevCenterName <String> -ProjectName <String> -UserId <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### List1ByDevCenter
```
Get-AzDevCenterUserDevBox -DevCenterName <String> -UserId <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetByDevCenter
```
Get-AzDevCenterUserDevBox -DevCenterName <String> -ProjectName <String> -UserId <String> -Name <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Gets a Dev Box

## EXAMPLES

### Example 1: List dev boxes by endpoint
```powershell
Get-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/"
```

This command lists dev boxes under the endpoint.

### Example 2: List dev boxes by endpoint and user id
```powershell
Get-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -UserId 00aa00aa-bb11-cc22-dd33-44ee44ee44ee
```

This command lists dev boxes under the endpoint assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

### Example 3: List dev boxes by endpoint, user id, and project
```powershell
Get-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -ProjectName DevProject -UserId "me"
```

This command lists dev boxes under the project "DevProject" assigned to the currently signed-in user.

### Example 4: List dev boxes by dev center name
```powershell
Get-AzDevCenterUserDevBox -DevCenterName Contoso
```

This command lists dev boxes under the dev center "Contoso".

### Example 5: List dev boxes by dev center and user id
```powershell
Get-AzDevCenterUserDevBox -DevCenterName Contoso -UserId "me"
```

This command lists dev boxes under the dev center "Contoso" assigned to the currently signed-in user.

### Example 6: List dev boxes by dev center, user id, and project
```powershell
Get-AzDevCenterUserDevBox -DevCenterName Contoso -ProjectName DevProject -UserId 00aa00aa-bb11-cc22-dd33-44ee44ee44ee
```

This command lists dev boxes under the project "DevProject" assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

### Example 7: Get a dev box by endpoint
```powershell
Get-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -ProjectName DevProject -UserId 00aa00aa-bb11-cc22-dd33-44ee44ee44ee -Name myDevBox
```

This command gets the dev box "myDevBox" assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

### Example 8: Get a dev box by dev center
```powershell
Get-AzDevCenterUserDevBox -DevCenterName Contoso -ProjectName DevProject -UserId "me" -Name myDevBox
```

This command gets the dev box "myDevBox" assigned to the currently signed-in user.

### Example 9: Get a dev box by endpoint and InputObject
```powershell
$devBoxInput = @{"DevBoxName" = "myDevBox"; "UserId" = "me"; "ProjectName" = "DevProject" }
Get-AzDevCenterUserDevBox -Endpoint "https://8a40af38-3b4c-4672-a6a4-5e964b1870ed-contosodevcenter.centralus.devcenter.azure.com/" -InputObject $devBoxInput
```

This command gets the dev box "myDevBox" assigned to the currently signed-in user.

### Example 10: Get a dev box by dev center and InputObject
```powershell
$devBoxInput = @{"DevBoxName" = "myDevBox"; "UserId" = "00aa00aa-bb11-cc22-dd33-44ee44ee44ee"; "ProjectName" = "DevProject" }
Get-AzDevCenterUserDevBox -DevCenterName Contoso -InputObject $devBoxInput
```

This command gets the dev box "myDevBox" assigned to user "00aa00aa-bb11-cc22-dd33-44ee44ee44ee".

## PARAMETERS

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

### -DevCenterName
The DevCenter upon which to execute operations.

```yaml
Type: System.String
Parameter Sets: GetViaIdentityByDevCenter, ListByDevCenter, List2ByDevCenter, List1ByDevCenter, GetByDevCenter
Aliases: DevCenter

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint
The DevCenter-specific URI to operate on.

```yaml
Type: System.String
Parameter Sets: List, Get, GetViaIdentity, List1, List2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DevCenterdata.Models.IDevCenterdataIdentity
Parameter Sets: GetViaIdentity, GetViaIdentityByDevCenter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The name of a Dev Box.

```yaml
Type: System.String
Parameter Sets: Get, GetByDevCenter
Aliases: DevBoxName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectName
The DevCenter Project upon which to execute operations.

```yaml
Type: System.String
Parameter Sets: Get, List2, List2ByDevCenter, GetByDevCenter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserId
The AAD object id of the user.
If value is 'me', the identity is taken from the authentication context.

```yaml
Type: System.String
Parameter Sets: Get, List1, List2, List2ByDevCenter, List1ByDevCenter, GetByDevCenter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DevCenterdata.Models.IDevCenterdataIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DevCenterdata.Models.Api20231001Preview.IDevBox

## NOTES

## RELATED LINKS
