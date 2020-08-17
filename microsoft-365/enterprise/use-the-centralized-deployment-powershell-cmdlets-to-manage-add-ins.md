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
description: Use os cmdlets do PowerShell de implantação centralizada para ajudá-lo a implantar e gerenciar suplementos do Office para sua organização do Microsoft 365.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687407"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="81176-103">Usar os cmdlets do PowerShell de Implantação Centralizada para gerenciar suplementos</span><span class="sxs-lookup"><span data-stu-id="81176-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="81176-104">Como um administrador global do Microsoft 365, você pode implantar suplementos do Office para usuários por meio do recurso de implantação centralizada (Confira [implantar suplementos do Office no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span><span class="sxs-lookup"><span data-stu-id="81176-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span></span> <span data-ttu-id="81176-105">Além de implantar os suplementos do Office por meio do centro de administração do Microsoft 365, você também pode usar o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81176-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="81176-106">Instale o [módulo de implantação de suplemento centralizado do O365 para o Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="81176-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="81176-107">Depois de baixar o módulo, abra uma janela do Windows PowerShell regular e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="81176-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="81176-108">Conectar-se usando suas credenciais de administrador</span><span class="sxs-lookup"><span data-stu-id="81176-108">Connect using your admin credentials</span></span>

<span data-ttu-id="81176-109">Antes de poder usar os cmdlets de implantação centralizada, você precisa entrar.</span><span class="sxs-lookup"><span data-stu-id="81176-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="81176-110">Inicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81176-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="81176-111">Conecte-se ao PowerShell usando as credenciais de administrador da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="81176-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="81176-112">Execute o cmdlet a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="81176-113">Na página **Inserir credenciais** , digite suas credenciais de administrador global do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81176-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="81176-114">Como alternativa, você pode inserir suas credenciais diretamente no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="81176-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="81176-115">Execute o cmdlet a seguir especificando suas credenciais de administrador de empresa como um objeto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="81176-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="81176-116">Para obter mais informações sobre como usar o PowerShell, consulte [conectar-se ao Microsoft 365 com o PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="81176-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="81176-117">Carregar um manifesto de suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-117">Upload an add-in manifest</span></span>

<span data-ttu-id="81176-118">Execute o cmdlet **New-OrganizationAdd-in** para carregar um manifesto de suplemento a partir de um caminho, que pode ser um local de arquivo ou uma URL.</span><span class="sxs-lookup"><span data-stu-id="81176-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="81176-119">O exemplo a seguir mostra um local de arquivo para o valor do parâmetro  _ManifestPath_ .</span><span class="sxs-lookup"><span data-stu-id="81176-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="81176-120">Você também pode executar o cmdlet **New-OrganizationAdd-in** para carregar um suplemento e atribuí-lo a usuários ou grupos diretamente usando o parâmetro  _Members_ , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="81176-121">Separe os endereços de email dos membros com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="81176-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="81176-122">Carregar um suplemento da Office Store</span><span class="sxs-lookup"><span data-stu-id="81176-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="81176-123">Execute o cmdlet **New-OrganizationAddIn** para carregar um manifesto da Office Store.</span><span class="sxs-lookup"><span data-stu-id="81176-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="81176-124">No exemplo a seguir, o cmdlet **New-OrganizationAddIn** especifica o AssetID de um suplemento para um local dos Estados Unidos e o mercado de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="81176-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="81176-125">Para determinar o valor para o parâmetro  _AssetID_ , você pode copiá-lo da URL da página da Web da Office Store para o suplemento.</span><span class="sxs-lookup"><span data-stu-id="81176-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="81176-126">AssetIds sempre começa com "WA" seguido por um número.</span><span class="sxs-lookup"><span data-stu-id="81176-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="81176-127">Por exemplo, no exemplo anterior, a origem para o valor AssetID de WA104099688 é a URL da página da Web da Office Store para o suplemento: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="81176-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="81176-128">Os valores para o parâmetro  _locale_ e o parâmetro  _ContentMarket_ são idênticos e indicam o país/região para o qual você está tentando instalar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="81176-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="81176-129">O formato é en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="81176-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="81176-130">e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="81176-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="81176-131">Os suplementos carregados da Office Store serão atualizados automaticamente em alguns dias da última atualização disponível na Office Store.</span><span class="sxs-lookup"><span data-stu-id="81176-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="81176-132">Obter detalhes de um suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-132">Get details of an add-in</span></span>

<span data-ttu-id="81176-133">Execute o cmdlet **Get-OrganizationAddIn** conforme mostrado abaixo para obter detalhes de todos os suplementos carregados no locatário, incluindo a ID de produto de um suplemento.</span><span class="sxs-lookup"><span data-stu-id="81176-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="81176-134">Execute o cmdlet **Get-OrganizationAddIn** com um valor para o parâmetro  _ProductID_ para especificar o suplemento para o qual você deseja recuperar detalhes.</span><span class="sxs-lookup"><span data-stu-id="81176-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="81176-135">Para obter detalhes completos de todos os suplementos, além dos usuários e grupos atribuídos, canalize a saída do cmdlet **Get-OrganizationAddIn** para o cmdlet Format-List, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="81176-136">Ativar ou desativar um suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="81176-137">Para desativar um suplemento para que os usuários e grupos atribuídos a ele não tenham mais acesso, execute o cmdlet **set-OrganizationAddIn** com o parâmetro  _ProductID_ e o parâmetro  _Enabled_ definido  `$false` como, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="81176-138">Para ativar um suplemento novamente, execute o mesmo cmdlet com o parâmetro  _Enabled_ definido como  `$true` .</span><span class="sxs-lookup"><span data-stu-id="81176-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="81176-139">Adicionar ou remover usuários de um suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="81176-140">Para adicionar usuários e grupos a um suplemento específico, execute o cmdlet **set-OrganizationAddInAssignments** com os parâmetros  _ProductID_,  _Add_e  _Members_ .</span><span class="sxs-lookup"><span data-stu-id="81176-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="81176-141">Separe os endereços de email dos membros com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="81176-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="81176-142">Para remover usuários e grupos, execute o mesmo cmdlet usando o parâmetro  _Remove_ .</span><span class="sxs-lookup"><span data-stu-id="81176-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="81176-143">Para atribuir um suplemento a todos os usuários no locatário, execute o mesmo cmdlet usando o parâmetro  _AssignToEveryone_ com o valor definido como  `$true` .</span><span class="sxs-lookup"><span data-stu-id="81176-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="81176-144">Para não atribuir um suplemento a todos e reverter para os usuários e grupos atribuídos anteriormente, você pode executar o mesmo cmdlet e desativar o parâmetro  _AssignToEveryone_ definindo seu valor como  `$false` .</span><span class="sxs-lookup"><span data-stu-id="81176-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="81176-145">Atualizar um suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-145">Update an add-in</span></span>

<span data-ttu-id="81176-146">Para atualizar um suplemento de um manifesto, execute o cmdlet **set-OrganizationAddIn** com os parâmetros  _ProductID_,  _ManifestPath_e  _locale_ , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="81176-147">Os suplementos carregados da Office Store serão atualizados automaticamente em alguns dias da última atualização disponível na Office Store.</span><span class="sxs-lookup"><span data-stu-id="81176-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="81176-148">Excluir um suplemento</span><span class="sxs-lookup"><span data-stu-id="81176-148">Delete an add-in</span></span>

<span data-ttu-id="81176-149">Para excluir um suplemento, execute o cmdlet **Remove-OrganizationAddIn** com o parâmetro  _ProductID_ , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81176-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="81176-150">Obter ajuda detalhada para cada cmdlet</span><span class="sxs-lookup"><span data-stu-id="81176-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="81176-151">Você pode examinar a ajuda detalhada para cada cmdlet usando o cmdlet Get-Help.</span><span class="sxs-lookup"><span data-stu-id="81176-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="81176-152">Por exemplo, o cmdlet a seguir fornece informações detalhadas sobre o cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="81176-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```

