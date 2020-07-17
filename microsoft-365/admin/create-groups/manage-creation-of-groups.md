---
title: Gerenciar quem pode criar grupos
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Saiba como controlar quais usuários podem criar grupos do Microsoft 365.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761669"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="4e15d-103">Gerenciar quem pode criar grupos</span><span class="sxs-lookup"><span data-stu-id="4e15d-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="4e15d-104">Como é muito fácil para os usuários criarem grupos do Microsoft 365, você não é inundado com solicitações para criá-los em nome de outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="4e15d-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="4e15d-105">Dependendo da sua empresa, no entanto, talvez você queira controlar quem tem a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="4e15d-106">Este artigo explica como desabilitar a capacidade de criar grupos em todos os serviços do Microsoft 365 que usam grupos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="4e15d-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="4e15d-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="4e15d-107">Outlook</span></span>
    
- <span data-ttu-id="4e15d-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e15d-108">SharePoint</span></span>
    
- <span data-ttu-id="4e15d-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="4e15d-109">Yammer</span></span>
    
- <span data-ttu-id="4e15d-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e15d-110">Microsoft Teams</span></span>

- <span data-ttu-id="4e15d-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4e15d-111">Microsoft Stream</span></span>

- <span data-ttu-id="4e15d-112">Planner</span><span class="sxs-lookup"><span data-stu-id="4e15d-112">Planner</span></span>
    
- <span data-ttu-id="4e15d-113">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4e15d-113">PowerBI</span></span>

- <span data-ttu-id="4e15d-114">Projeto para a Web e o mapa</span><span class="sxs-lookup"><span data-stu-id="4e15d-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="4e15d-115">Você pode restringir a criação de grupos do Microsoft 365 aos membros de um determinado grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4e15d-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="4e15d-116">Para configurar isso, use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e15d-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="4e15d-117">Este artigo orienta você pelas etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="4e15d-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="4e15d-118">As etapas neste artigo não impedem que os membros de determinadas funções criem grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="4e15d-119">Os administradores globais podem criar grupos por meio de qualquer meio, como o centro de administração do 365, o Planner, o Microsoft Teams, o Exchange e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e15d-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="4e15d-120">Outras funções podem criar grupos por meio limitado, listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="4e15d-121">Administrador do Exchange: centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e15d-122">Suporte à camada 1 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e15d-123">Suporte à camada 2 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e15d-124">Gravadores de diretório: Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="4e15d-125">Administrador do SharePoint: centro de administração do SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4e15d-126">Administrador do teams Service: centro de administração do Microsoft Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4e15d-127">Administrador de gerenciamento de usuários: centro de administração do Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e15d-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="4e15d-128">Se você for um membro de uma dessas funções, poderá criar grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="4e15d-129">Os usuários que possuem essa função podem criar grupos conectados no Yammer, independentemente de qualquer configuração do PowerShell que possa impedir a criação.</span><span class="sxs-lookup"><span data-stu-id="4e15d-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4e15d-130">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="4e15d-130">Licensing requirements</span></span>

<span data-ttu-id="4e15d-131">Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:</span><span class="sxs-lookup"><span data-stu-id="4e15d-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4e15d-132">O administrador que configura essas definições de criação de grupos</span><span class="sxs-lookup"><span data-stu-id="4e15d-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="4e15d-133">Os membros do grupo de segurança que têm permissão para criar grupos</span><span class="sxs-lookup"><span data-stu-id="4e15d-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="4e15d-134">Consulte [atribuir ou remover licenças no portal do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.</span><span class="sxs-lookup"><span data-stu-id="4e15d-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="4e15d-135">As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas:</span><span class="sxs-lookup"><span data-stu-id="4e15d-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4e15d-136">Pessoas que são membros de grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="4e15d-137">Etapa 1: criar um grupo de segurança para os usuários que precisam criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e15d-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="4e15d-138">Somente um grupo de segurança em sua organização pode ser usado para controlar quem é capaz de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="4e15d-139">Mas você pode aninhar outros grupos de segurança como membros deste grupo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="4e15d-140">Por exemplo, o grupo chamado Permitir a criação de grupo é o grupo de segurança designado e os grupos chamados Usuários do Microsoft Planner e Usuários do Exchange Online são membros daquele grupo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="4e15d-141">Os administradores nas funções listadas acima não precisam ser membros desse grupo: Eles retêm a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e15d-142">Certifique-se de usar um **grupo de segurança** para restringir quem pode criar grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="4e15d-143">Se você tentar usar um grupo do Microsoft 365, os membros não poderão criar um grupo do SharePoint, pois ele verifica se há um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4e15d-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="4e15d-144">No centro de administração, vá para a página grupos de **grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="4e15d-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="4e15d-145">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="4e15d-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="4e15d-146">Escolha **segurança** como o tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="4e15d-147">Lembre-se do nome do grupo!</span><span class="sxs-lookup"><span data-stu-id="4e15d-147">Remember the name of the group!</span></span> <span data-ttu-id="4e15d-148">Você precisará disso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e15d-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="4e15d-149">Conclua a configuração do grupo de segurança, adicionando pessoas ou outros grupos de segurança que você deseja poder criar grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="4e15d-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="4e15d-150">Para obter instruções detalhadas, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="4e15d-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="4e15d-151">Etapa 2: Executar comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e15d-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="4e15d-152">Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:</span><span class="sxs-lookup"><span data-stu-id="4e15d-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="4e15d-153">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="4e15d-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="4e15d-154">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="4e15d-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="4e15d-155">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="4e15d-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="4e15d-156">Copie o script abaixo para um editor de texto, como o bloco de notas, ou o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="4e15d-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="4e15d-157">Substitua *\<SecurityGroupName\>* pelo nome do grupo de segurança que você criou.</span><span class="sxs-lookup"><span data-stu-id="4e15d-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="4e15d-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4e15d-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="4e15d-159">Salve o arquivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="4e15d-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="4e15d-160">Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="4e15d-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="4e15d-161">Execute o script digitando:</span><span class="sxs-lookup"><span data-stu-id="4e15d-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="4e15d-162">e [entre com sua conta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="4e15d-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="4e15d-163">A última linha do script exibirá as configurações atualizadas:</span><span class="sxs-lookup"><span data-stu-id="4e15d-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="4e15d-165">Se no futuro você quiser alterar o grupo de segurança usado, poderá executar novamente o script com o nome do novo grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4e15d-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="4e15d-166">Se você deseja desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, defina $GroupName como "" e $AllowGroupCreation como "true" e execute novamente o script.</span><span class="sxs-lookup"><span data-stu-id="4e15d-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="4e15d-167">Etapa 3: Verifique se funciona</span><span class="sxs-lookup"><span data-stu-id="4e15d-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="4e15d-168">As alterações podem levar trinta minutos ou mais para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="4e15d-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="4e15d-169">Você pode verificar as novas configurações fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4e15d-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="4e15d-170">Entre com uma conta de usuário de alguém que não deve ter a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="4e15d-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="4e15d-171">Ou seja, eles não são membros do grupo de segurança que você criou ou de um administrador.</span><span class="sxs-lookup"><span data-stu-id="4e15d-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="4e15d-172">Selecione o bloco do **Planner** .</span><span class="sxs-lookup"><span data-stu-id="4e15d-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="4e15d-173">No Planner, selecione **novo plano** no painel de navegação à esquerda para criar um plano.</span><span class="sxs-lookup"><span data-stu-id="4e15d-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="4e15d-174">Você deve obter uma mensagem informando que o plano e a criação de grupos estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="4e15d-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="4e15d-175">Tente o mesmo procedimento novamente com um membro do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4e15d-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="4e15d-176">Se os membros do grupo de segurança não puderem criar grupos, verifique se eles não estão sendo bloqueados por meio da [política de caixa de correio do OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="4e15d-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="4e15d-177">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4e15d-177">Related articles</span></span>

[<span data-ttu-id="4e15d-178">Introdução ao Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e15d-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="4e15d-179">Configurar o gerenciamento de grupo de autoatendimento no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e15d-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="4e15d-180">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4e15d-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="4e15d-181">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="4e15d-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
