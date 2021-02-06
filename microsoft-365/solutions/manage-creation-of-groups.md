---
title: Gerenciar quem pode criar Grupos do Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Saiba como controlar quais usuários podem criar Grupos do Microsoft 365.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122379"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="55608-103">Gerenciar quem pode criar Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55608-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="55608-104">Por padrão, todos os usuários podem criar grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55608-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="55608-105">Essa é a abordagem recomendada porque permite que os usuários comecem a colaborar sem a necessidade de assistência da TI.</span><span class="sxs-lookup"><span data-stu-id="55608-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="55608-106">Se a sua empresa exigir que você restrinja quem pode criar grupos, você poderá fazer isso seguindo os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="55608-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="55608-107">Quando você limita quem pode criar um grupo, ele afeta todos os serviços que dependem de grupos para acesso, incluindo:</span><span class="sxs-lookup"><span data-stu-id="55608-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="55608-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="55608-108">Outlook</span></span>
- <span data-ttu-id="55608-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="55608-109">SharePoint</span></span>
- <span data-ttu-id="55608-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="55608-110">Yammer</span></span>
- <span data-ttu-id="55608-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55608-111">Microsoft Teams</span></span>
- <span data-ttu-id="55608-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="55608-112">Microsoft Stream</span></span>
- <span data-ttu-id="55608-113">Planner</span><span class="sxs-lookup"><span data-stu-id="55608-113">Planner</span></span>
- <span data-ttu-id="55608-114">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="55608-114">Power BI (classic)</span></span>
- <span data-ttu-id="55608-115">Project para a Web/Roteiro</span><span class="sxs-lookup"><span data-stu-id="55608-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="55608-116">Você pode restringir a criação do Grupo do Microsoft 365 aos membros de um grupo ou grupo de segurança específico do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55608-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="55608-117">Para configurar isso, use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55608-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="55608-118">Este artigo orienta você pelas etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="55608-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="55608-119">As etapas neste artigo não impedirão membros de determinadas funções de criar Grupos.</span><span class="sxs-lookup"><span data-stu-id="55608-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="55608-120">Os administradores globais do Office 365 podem criar Grupos por qualquer meio, como o centro de administração do Microsoft 365, o Planner, o Teams, o Exchange e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="55608-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="55608-121">Outras funções podem criar Grupos por meios limitados, listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="55608-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="55608-122">Administrador do Exchange: Centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="55608-123">Suporte ao Nível 1 do Parceiro: Centro de administração do Microsoft 365, Centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="55608-124">Suporte ao Nível 2 do Parceiro: Centro de administração do Microsoft 365, Centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="55608-125">Autores de diretório: Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="55608-126">Administrador do SharePoint: Centro de administração do SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="55608-127">Administrador de Serviços do Teams: Centro de administração do Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="55608-128">Administrador de Gerenciamento de Usuários: Centro de administração do Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="55608-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="55608-129">Se você for membro de uma dessas funções, poderá criar Grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.</span><span class="sxs-lookup"><span data-stu-id="55608-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="55608-130">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="55608-130">Licensing requirements</span></span>

<span data-ttu-id="55608-131">Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças EDU básicas do Azure AD atribuídas a elas:</span><span class="sxs-lookup"><span data-stu-id="55608-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="55608-132">O administrador que define essas configurações de criação de grupo</span><span class="sxs-lookup"><span data-stu-id="55608-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="55608-133">Os membros do grupo que têm permissão para criar grupos</span><span class="sxs-lookup"><span data-stu-id="55608-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="55608-134">Confira Atribuir ou remover licenças no portal do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.</span><span class="sxs-lookup"><span data-stu-id="55608-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="55608-135">As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas a elas:</span><span class="sxs-lookup"><span data-stu-id="55608-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="55608-136">Pessoas que são membros dos grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.</span><span class="sxs-lookup"><span data-stu-id="55608-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="55608-137">Etapa 1: Criar um grupo para usuários que precisam criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55608-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="55608-138">Somente um grupo em sua organização pode ser usado para controlar quem é capaz de criar Grupos.</span><span class="sxs-lookup"><span data-stu-id="55608-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="55608-139">Porém, você pode aninhar outros grupos como membros desse grupo.</span><span class="sxs-lookup"><span data-stu-id="55608-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="55608-140">Os administradores nas funções listadas acima não precisam ser membros desse grupo: eles mantêm sua capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="55608-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="55608-141">No centro de administração, vá para a página [Grupos.](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="55608-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="55608-142">Clique em **Adicionar um Grupo.**</span><span class="sxs-lookup"><span data-stu-id="55608-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="55608-143">Escolha o tipo de grupo que você deseja.</span><span class="sxs-lookup"><span data-stu-id="55608-143">Choose the group type you want.</span></span> <span data-ttu-id="55608-144">Lembre-se do nome do grupo!</span><span class="sxs-lookup"><span data-stu-id="55608-144">Remember the name of the group!</span></span> <span data-ttu-id="55608-145">Você precisará disso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="55608-145">You'll need it later.</span></span>

4. <span data-ttu-id="55608-146">Termine de configurar o grupo, adicionando pessoas ou outros grupos que você deseja que sejam capazes de criar grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55608-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="55608-147">Para obter instruções detalhadas, confira Criar, editar ou excluir um grupo de segurança no centro de administração do [Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="55608-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="55608-148">Etapa 2: Executar comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="55608-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="55608-149">Você deve usar a versão de visualização do [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado no nível do grupo:</span><span class="sxs-lookup"><span data-stu-id="55608-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="55608-150">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="55608-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="55608-151">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="55608-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="55608-152">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="55608-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="55608-153">Copie o script abaixo em um editor de texto, como o Bloco de Notas ou o [ISE do Windows PowerShell.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="55608-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="55608-154">Substitua *\<GroupName\>* pelo nome do grupo que você criou.</span><span class="sxs-lookup"><span data-stu-id="55608-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="55608-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="55608-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="55608-156">Salve o arquivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="55608-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="55608-157">Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="55608-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="55608-158">Execute o script digitando:</span><span class="sxs-lookup"><span data-stu-id="55608-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="55608-159">e [entre com sua conta de administrador](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="55608-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="55608-160">A última linha do script exibirá as configurações atualizadas:</span><span class="sxs-lookup"><span data-stu-id="55608-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="55608-162">Se, no futuro, você quiser alterar qual grupo é usado, poderá reruncar o script com o nome do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="55608-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="55608-163">Se você quiser desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, de definir $GroupName como "" e $AllowGroupCreation como "True" e novamente o script.</span><span class="sxs-lookup"><span data-stu-id="55608-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="55608-164">Etapa 3: Verifique se funciona</span><span class="sxs-lookup"><span data-stu-id="55608-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="55608-165">As alterações podem levar trinta minutos ou mais para surcarem efeito.</span><span class="sxs-lookup"><span data-stu-id="55608-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="55608-166">Você pode verificar as novas configurações fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55608-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="55608-167">Entre no Microsoft 365 com uma conta de usuário de alguém que NÃO deve ter a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="55608-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="55608-168">Ou seja, eles não são membros do grupo que você criou ou são administradores.</span><span class="sxs-lookup"><span data-stu-id="55608-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="55608-169">Selecione **oile do Planejador.**</span><span class="sxs-lookup"><span data-stu-id="55608-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="55608-170">No Planner, selecione **Novo Plano** na navegação à esquerda para criar um plano.</span><span class="sxs-lookup"><span data-stu-id="55608-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="55608-171">Você deve receber uma mensagem de que o plano e a criação de grupo estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="55608-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="55608-172">Tente o mesmo procedimento novamente com um membro do grupo.</span><span class="sxs-lookup"><span data-stu-id="55608-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="55608-173">Se os membros do grupo não conseguem criar grupos, verifique se eles não estão sendo bloqueados por meio da política de caixa de correio do [OWA.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="55608-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="55608-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="55608-174">Related topics</span></span>

[<span data-ttu-id="55608-175">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="55608-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="55608-176">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="55608-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="55608-177">Introdução ao Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="55608-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="55608-178">Configurar o gerenciamento de grupos de autoatendura no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="55608-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="55608-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="55608-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="55608-180">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="55608-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
