---
title: Gerenciar quem pode criar grupos do Microsoft 365
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
description: Saiba como controlar quais usuários podem criar grupos do Microsoft 365.
ms.openlocfilehash: 2954f68dce289d43b37bf8f5c6ff43fe1b5c48c7
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613555"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="7b505-103">Gerenciar quem pode criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b505-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="7b505-104">Por padrão, todos os usuários podem criar grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b505-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="7b505-105">Essa é a abordagem recomendada porque permite que os usuários comecem a colaborar sem precisar de assistência.</span><span class="sxs-lookup"><span data-stu-id="7b505-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="7b505-106">Se sua empresa requer que você restrinja quem pode criar grupos, faça isso seguindo os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7b505-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="7b505-107">Quando você limita quem pode criar um grupo, ele afeta todos os serviços que dependem de grupos para acesso, incluindo:</span><span class="sxs-lookup"><span data-stu-id="7b505-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="7b505-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="7b505-108">Outlook</span></span>
- <span data-ttu-id="7b505-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b505-109">SharePoint</span></span>
- <span data-ttu-id="7b505-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="7b505-110">Yammer</span></span>
- <span data-ttu-id="7b505-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b505-111">Microsoft Teams</span></span>
- <span data-ttu-id="7b505-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7b505-112">Microsoft Stream</span></span>
- <span data-ttu-id="7b505-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7b505-113">Planner</span></span>
- <span data-ttu-id="7b505-114">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="7b505-114">Power BI (classic)</span></span>
- <span data-ttu-id="7b505-115">Projeto para a Web/mapa</span><span class="sxs-lookup"><span data-stu-id="7b505-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="7b505-116">Você pode restringir a criação de grupos do Microsoft 365 aos membros de um determinado grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7b505-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="7b505-117">Para configurar isso, use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b505-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="7b505-118">Este artigo orienta você pelas etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="7b505-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="7b505-119">As etapas neste artigo não impedem que os membros de determinadas funções criem grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7b505-120">Os administradores globais do Office 365 podem criar grupos por meio de qualquer meio, como o centro de administração do Microsoft 365, o Planner, o Teams, o Exchange e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7b505-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7b505-121">Outras funções podem criar grupos por meio limitado, listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="7b505-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="7b505-122">Administrador do Exchange: centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7b505-123">Suporte à camada 1 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7b505-124">Suporte à camada 2 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7b505-125">Gravadores de diretório: Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="7b505-126">Administrador do SharePoint: centro de administração do SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="7b505-127">Administrador do teams Service: centro de administração do Microsoft Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="7b505-128">Administrador de gerenciamento de usuários: centro de administração do Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b505-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="7b505-129">Se você for um membro de uma dessas funções, poderá criar grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.</span><span class="sxs-lookup"><span data-stu-id="7b505-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7b505-130">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="7b505-130">Licensing requirements</span></span>

<span data-ttu-id="7b505-131">Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:</span><span class="sxs-lookup"><span data-stu-id="7b505-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7b505-132">O administrador que configura essas definições de criação de grupos</span><span class="sxs-lookup"><span data-stu-id="7b505-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7b505-133">Os membros do grupo de segurança que têm permissão para criar grupos</span><span class="sxs-lookup"><span data-stu-id="7b505-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="7b505-134">Consulte [atribuir ou remover licenças no portal do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.</span><span class="sxs-lookup"><span data-stu-id="7b505-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="7b505-135">As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas:</span><span class="sxs-lookup"><span data-stu-id="7b505-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7b505-136">Pessoas que são membros de grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="7b505-137">Etapa 1: criar um grupo de segurança para os usuários que precisam criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b505-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="7b505-138">Somente um grupo de segurança em sua organização pode ser usado para controlar quem é capaz de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7b505-139">Mas você pode aninhar outros grupos de segurança como membros deste grupo.</span><span class="sxs-lookup"><span data-stu-id="7b505-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="7b505-140">Os administradores nas funções listadas acima não precisam ser membros desse grupo: Eles retêm a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b505-141">Certifique-se de usar um **grupo de segurança** para restringir quem pode criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="7b505-142">Não há suporte para o uso de um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b505-142">Using a Microsoft 365 group is not supported.</span></span>

1. <span data-ttu-id="7b505-143">No centro de administração, vá para a [página grupos](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="7b505-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="7b505-144">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="7b505-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7b505-145">Escolha **segurança** como o tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="7b505-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="7b505-146">Lembre-se do nome do grupo!</span><span class="sxs-lookup"><span data-stu-id="7b505-146">Remember the name of the group!</span></span> <span data-ttu-id="7b505-147">Você precisará disso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7b505-147">You'll need it later.</span></span>

4. <span data-ttu-id="7b505-148">Conclua a configuração do grupo de segurança, adicionando pessoas ou outros grupos de segurança que você deseja poder criar grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b505-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="7b505-149">Para obter instruções detalhadas, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="7b505-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="7b505-150">Etapa 2: Executar comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b505-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="7b505-151">Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:</span><span class="sxs-lookup"><span data-stu-id="7b505-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7b505-152">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="7b505-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7b505-153">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="7b505-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7b505-154">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="7b505-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="7b505-155">Copie o script abaixo para um editor de texto, como o bloco de notas, ou o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="7b505-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7b505-156">Substitua *\<SecurityGroupName\>* pelo nome do grupo de segurança que você criou.</span><span class="sxs-lookup"><span data-stu-id="7b505-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="7b505-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b505-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7b505-158">Salve o arquivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="7b505-158">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="7b505-159">Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="7b505-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7b505-160">Execute o script digitando:</span><span class="sxs-lookup"><span data-stu-id="7b505-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7b505-161">e [entre com sua conta de administrador](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="7b505-161">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
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

<span data-ttu-id="7b505-162">A última linha do script exibirá as configurações atualizadas:</span><span class="sxs-lookup"><span data-stu-id="7b505-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7b505-164">Se no futuro você quiser alterar o grupo de segurança usado, poderá executar novamente o script com o nome do novo grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7b505-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="7b505-165">Se você deseja desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, defina $GroupName como "" e $AllowGroupCreation como "true" e execute novamente o script.</span><span class="sxs-lookup"><span data-stu-id="7b505-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="7b505-166">Etapa 3: Verifique se funciona</span><span class="sxs-lookup"><span data-stu-id="7b505-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="7b505-167">As alterações podem levar trinta minutos ou mais para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="7b505-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="7b505-168">Você pode verificar as novas configurações fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b505-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="7b505-169">Entre no Microsoft 365 com uma conta de usuário de alguém que não tenha a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7b505-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7b505-170">Ou seja, eles não são membros do grupo de segurança que você criou ou de um administrador.</span><span class="sxs-lookup"><span data-stu-id="7b505-170">That is, they are not a member of the security group you created or an administrator.</span></span>

2. <span data-ttu-id="7b505-171">Selecione o bloco do **Planner** .</span><span class="sxs-lookup"><span data-stu-id="7b505-171">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="7b505-172">No Planner, selecione **novo plano** no painel de navegação à esquerda para criar um plano.</span><span class="sxs-lookup"><span data-stu-id="7b505-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="7b505-173">Você deve obter uma mensagem informando que o plano e a criação de grupos estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="7b505-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7b505-174">Tente o mesmo procedimento novamente com um membro do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7b505-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="7b505-175">Se os membros do grupo de segurança não puderem criar grupos, verifique se eles não estão sendo bloqueados por meio da [política de caixa de correio do OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="7b505-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b505-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7b505-176">Related topics</span></span>

[<span data-ttu-id="7b505-177">Passo a passo de planejamento de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="7b505-177">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7b505-178">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="7b505-178">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="7b505-179">Introdução ao Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b505-179">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7b505-180">Configurar o gerenciamento de grupo de autoatendimento no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b505-180">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7b505-181">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7b505-181">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7b505-182">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="7b505-182">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
