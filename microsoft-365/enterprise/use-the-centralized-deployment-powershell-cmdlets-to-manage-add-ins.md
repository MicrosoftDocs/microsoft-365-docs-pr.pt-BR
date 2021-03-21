---
title: Usar os cmdlets do PowerShell de Implantação Centralizada para gerenciar suplementos
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Use os cmdlets do PowerShell de Implantação Centralizada para ajudá-lo a implantar e gerenciar os complementos do Office para sua organização do Microsoft 365.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924667"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Usar os cmdlets do PowerShell de Implantação Centralizada para gerenciar suplementos

Como administrador global do Microsoft 365, você pode implantar os complementos do Office para usuários por meio do recurso Implantação Centralizada (consulte [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)). Além de implantar os complementos do Office por meio do Centro de administração do Microsoft 365, você também pode usar o Microsoft PowerShell. Instale o Módulo de Implantação centralizado [Add-In O365 para Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Depois de baixar o módulo, abra uma janela Windows PowerShell regular e execute o seguinte cmdlet:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Conectar-se usando suas credenciais de administrador

Antes de poder usar os cmdlets de Implantação Centralizada, você precisa entrar.
  
1. Inicie o PowerShell.
    
2. Conecte-se ao PowerShell usando as credenciais de administrador da sua empresa. Execute o cmdlet a seguir.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Na página **Inserir Credenciais,** insira suas credenciais de administrador global do Microsoft 365. Como alternativa, você pode inserir suas credenciais diretamente no cmdlet. 
    
    Execute o cmdlet a seguir especificando as credenciais de administrador da empresa como um objeto PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Para obter mais informações sobre como usar o PowerShell, consulte [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md). 
  
## <a name="upload-an-add-in-manifest"></a>Carregar um manifesto do add-in

Execute o cmdlet **New-OrganizationAdd-In** para carregar um manifesto do complemento de um caminho, que pode ser um local de arquivo ou URL. O exemplo a seguir mostra um local de arquivo para o valor do _parâmetro ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Você também pode executar o cmdlet **New-OrganizationAdd-In** para carregar um complemento e atribuí-lo a usuários ou grupos diretamente usando o parâmetro  _Members,_ conforme mostrado no exemplo a seguir. Separe os endereços de email dos membros com uma vírgula. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Carregar um complemento da Office Store

Execute o cmdlet **New-OrganizationAddIn** para carregar um manifesto da Office Store.
  
No exemplo a seguir, o cmdlet **New-OrganizationAddIn** especifica a AssetId para um complemento para um local e mercado de conteúdo dos Estados Unidos.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Para determinar o valor do parâmetro  _AssetId,_ você pode copiá-lo da URL da página da Web da Office Store para o complemento. AssetIds sempre começam com "WA" seguido por um número. Por exemplo, no exemplo anterior, a origem do valor AssetId de WA104099688 é a URL da página da Web da Office Store para o complemento: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Os valores do parâmetro  _Locale_ e do  _parâmetro ContentMarket_ são idênticos e indicam o país/região de onde você está tentando instalar o complemento. O formato é en-US, fr-FR. e assim por diante. 
  
> [!NOTE]
> Os complementos carregados da Office Store serão atualizados automaticamente dentro de alguns dias após a atualização mais recente estar disponível na Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Obter detalhes de um complemento

Execute o cmdlet **Get-OrganizationAddIn** conforme mostrado abaixo para obter detalhes de todos os complementos carregados no locatário, incluindo a ID do produto de um complemento.
  
```powershell
Get-OrganizationAddIn
```

Execute o cmdlet **Get-OrganizationAddIn** com um valor para o parâmetro  _ProductId_ para especificar para qual complemento você deseja recuperar detalhes. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Para obter detalhes completos de todos os Format-List mais os usuários e grupos atribuídos, pipe a saída do cmdlet **Get-OrganizationAddIn** para o cmdlet Format-List, conforme mostrado no exemplo a seguir.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Ativar ou desativar um complemento

Para desativar um complemento para que os usuários e grupos atribuídos a ele não tenham mais acesso, execute o cmdlet **Set-OrganizationAddIn** com o parâmetro  _ProductId_ e o parâmetro  _Enabled_ definido como , conforme mostrado no exemplo a  `$false` seguir.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Para ativar novamente um complemento, execute o mesmo cmdlet com o parâmetro  _Enabled_ definido como  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Adicionar ou remover usuários de um complemento

Para adicionar usuários e grupos a um complemento específico, execute o cmdlet **Set-OrganizationAddInAssignments** com os parâmetros _ProductId,_ _Add_ e _Members._ Separe os endereços de email dos membros com uma vírgula. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Para remover usuários e grupos, execute o mesmo cmdlet usando o _parâmetro Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Para atribuir um complemento a todos os usuários no locatário, execute o mesmo cmdlet usando o  _parâmetro AssignToEveryone_ com o valor definido como  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Para não atribuir um complemento a todos e reverter para os usuários e grupos atribuídos anteriormente, você pode executar o mesmo cmdlet e desativar o parâmetro  _AssignToEveryone_ definindo seu valor como  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Atualizar um complemento

Para atualizar um complemento de um manifesto, execute o cmdlet **Set-OrganizationAddIn** com os parâmetros  _ProductId,_  _ManifestPath_ e  _Locale,_ conforme mostrado no exemplo a seguir. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Os complementos carregados da Office Store serão atualizados automaticamente dentro de alguns dias após a atualização mais recente estar disponível na Office Store. 
  
## <a name="delete-an-add-in"></a>Excluir um complemento

Para excluir um complemento, execute o cmdlet **Remove-OrganizationAddIn** com o parâmetro  _ProductId,_ conforme mostrado no exemplo a seguir. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>Obter ajuda detalhada para cada cmdlet

Você pode procurar ajuda detalhada para cada cmdlet usando o cmdlet Get-help. Por exemplo, o cmdlet a seguir fornece informações detalhadas sobre o Remove-OrganizationAddIn cmdlet.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```