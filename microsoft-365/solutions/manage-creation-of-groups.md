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
recommendations: false
description: Saiba como controlar quais usuários podem criar Microsoft 365 Grupos.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539174"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="64d19-103">Gerenciar quem pode criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="64d19-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="64d19-104">Por padrão, todos os usuários podem criar Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="64d19-105">Essa é a abordagem recomendada porque permite que os usuários comecem a colaborar sem exigir assistência de TI.</span><span class="sxs-lookup"><span data-stu-id="64d19-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="64d19-106">Se a sua empresa exigir que você restrinja quem pode criar grupos, você pode restringir Microsoft 365 criação de grupo aos membros de um grupo Microsoft 365 específico ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="64d19-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="64d19-107">Se você estiver preocupado com os usuários que criam equipes ou grupos que não estão em conformidade com seus padrões de negócios, considere exigir que os usuários concluam um curso de treinamento e, em seguida, adicione-os ao grupo de usuários permitidos.</span><span class="sxs-lookup"><span data-stu-id="64d19-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="64d19-108">Quando você limita quem pode criar um grupo, ele afeta todos os serviços que dependem de grupos para acesso, incluindo:</span><span class="sxs-lookup"><span data-stu-id="64d19-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="64d19-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="64d19-109">Outlook</span></span>
- <span data-ttu-id="64d19-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="64d19-110">SharePoint</span></span>
- <span data-ttu-id="64d19-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="64d19-111">Yammer</span></span>
- <span data-ttu-id="64d19-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64d19-112">Microsoft Teams</span></span>
- <span data-ttu-id="64d19-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="64d19-113">Microsoft Stream</span></span>
- <span data-ttu-id="64d19-114">Planner</span><span class="sxs-lookup"><span data-stu-id="64d19-114">Planner</span></span>
- <span data-ttu-id="64d19-115">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="64d19-115">Power BI (classic)</span></span>
- <span data-ttu-id="64d19-116">Project para a Web /Roteiro</span><span class="sxs-lookup"><span data-stu-id="64d19-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="64d19-117">As etapas deste artigo não impedirão que membros de determinadas funções de criação de Grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="64d19-118">Office 365 Os administradores globais podem criar Grupos Microsoft 365 centro de administração, Planner, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="64d19-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="64d19-119">Outras funções podem criar Grupos por meios limitados, listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="64d19-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="64d19-120">Exchange Administrador: Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="64d19-121">Suporte a Nível de Parceiro 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="64d19-122">Suporte ao Partner Tier 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="64d19-123">Redatores de diretório: Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="64d19-124">SharePoint Administrador: SharePoint Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="64d19-125">Teams Administrador de Serviços: Teams Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="64d19-126">Administrador do Usuário: Microsoft 365 Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="64d19-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="64d19-127">Se você for membro de uma dessas funções, poderá criar grupos Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.</span><span class="sxs-lookup"><span data-stu-id="64d19-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="64d19-128">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="64d19-128">Licensing requirements</span></span>

<span data-ttu-id="64d19-129">Para gerenciar quem cria grupos, as pessoas a seguir precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:</span><span class="sxs-lookup"><span data-stu-id="64d19-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="64d19-130">O administrador que configura essas configurações de criação de grupo</span><span class="sxs-lookup"><span data-stu-id="64d19-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="64d19-131">Os membros do grupo que têm permissão para criar grupos</span><span class="sxs-lookup"><span data-stu-id="64d19-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="64d19-132">Consulte [Atribuir ou remover licenças no portal Azure Active Directory para](/azure/active-directory/fundamentals/license-users-groups) obter mais detalhes sobre como atribuir licenças do Azure.</span><span class="sxs-lookup"><span data-stu-id="64d19-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="64d19-133">As pessoas a seguir não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas a elas:</span><span class="sxs-lookup"><span data-stu-id="64d19-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="64d19-134">Pessoas que são membros de Microsoft 365 grupos e que não têm a capacidade de criar outros grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="64d19-135">Etapa 1: criar um grupo para os usuários que precisam criar grupos Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="64d19-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="64d19-136">Somente um grupo em sua organização pode ser usado para controlar quem é capaz de criar Grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="64d19-137">Porém, você pode aninhar outros grupos como membros desse grupo.</span><span class="sxs-lookup"><span data-stu-id="64d19-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="64d19-138">Os administradores nas funções listadas acima não precisam ser membros desse grupo: eles retêm a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="64d19-139">No centro de administração, vá para a [página Grupos.](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="64d19-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="64d19-140">Clique em **Adicionar um Grupo**.</span><span class="sxs-lookup"><span data-stu-id="64d19-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="64d19-141">Escolha o tipo de grupo que você deseja.</span><span class="sxs-lookup"><span data-stu-id="64d19-141">Choose the group type you want.</span></span> <span data-ttu-id="64d19-142">Lembre-se do nome do grupo!</span><span class="sxs-lookup"><span data-stu-id="64d19-142">Remember the name of the group!</span></span> <span data-ttu-id="64d19-143">Você precisará disso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="64d19-143">You'll need it later.</span></span>

4. <span data-ttu-id="64d19-144">Termine de configurar o grupo, adicionando pessoas ou outros grupos que você deseja criar grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="64d19-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="64d19-145">Para obter instruções detalhadas, consulte [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="64d19-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="64d19-146">Etapa 2: Executar comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="64d19-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="64d19-147">Você deve usar a versão de visualização do Azure Active Directory PowerShell para [Graph (AzureAD) (nome](/powershell/azure/active-directory/install-adv2) do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado no nível de grupo:</span><span class="sxs-lookup"><span data-stu-id="64d19-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="64d19-148">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="64d19-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="64d19-149">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="64d19-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="64d19-150">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="64d19-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="64d19-151">Copie o script abaixo para um editor de texto, como Bloco de notas, ou o [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="64d19-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="64d19-152">Substitua *\<GroupName\>* pelo nome do grupo que você criou.</span><span class="sxs-lookup"><span data-stu-id="64d19-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="64d19-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="64d19-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="64d19-154">Salve o arquivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="64d19-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="64d19-155">Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="64d19-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="64d19-156">Execute o script digitando:</span><span class="sxs-lookup"><span data-stu-id="64d19-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="64d19-157">e [entre com sua conta de administrador quando](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) solicitado.</span><span class="sxs-lookup"><span data-stu-id="64d19-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="64d19-158">A última linha do script exibirá as configurações atualizadas:</span><span class="sxs-lookup"><span data-stu-id="64d19-158">The last line of the script will display the updated settings:</span></span>

![Captura de tela da saída de script do PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="64d19-160">Se no futuro você quiser alterar qual grupo é usado, você pode reprisar o script com o nome do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="64d19-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="64d19-161">Se você quiser desativar a restrição de criação de grupo e permitir novamente que todos os usuários criem grupos, de definir $GroupName como "" e $AllowGroupCreation como "True" e repetir o script.</span><span class="sxs-lookup"><span data-stu-id="64d19-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="64d19-162">Etapa 3: Verifique se funciona</span><span class="sxs-lookup"><span data-stu-id="64d19-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="64d19-163">As alterações podem levar trinta minutos ou mais para vigorar.</span><span class="sxs-lookup"><span data-stu-id="64d19-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="64d19-164">Você pode verificar as novas configurações fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64d19-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="64d19-165">Entre no Microsoft 365 com uma conta de usuário de alguém que NÃO deve ter a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="64d19-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="64d19-166">Ou seja, eles não são um membro do grupo que você criou ou um administrador.</span><span class="sxs-lookup"><span data-stu-id="64d19-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="64d19-167">Selecione o **azulejo do Planner.**</span><span class="sxs-lookup"><span data-stu-id="64d19-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="64d19-168">No Planner, selecione **Novo Plano** na navegação à esquerda para criar um plano.</span><span class="sxs-lookup"><span data-stu-id="64d19-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="64d19-169">Você deve receber uma mensagem de que o plano e a criação de grupo estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="64d19-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="64d19-170">Tente o mesmo procedimento novamente com um membro do grupo.</span><span class="sxs-lookup"><span data-stu-id="64d19-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="64d19-171">Se os membros do grupo não são capazes de criar grupos, verifique se eles não estão sendo bloqueados por meio da política de caixa de [correio do OWA](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="64d19-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="64d19-172">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="64d19-172">Related topics</span></span>

[<span data-ttu-id="64d19-173">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="64d19-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="64d19-174">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="64d19-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="64d19-175">Introdução ao Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="64d19-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="64d19-176">Configurar o gerenciamento de grupo de autoatend Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="64d19-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="64d19-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="64d19-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="64d19-178">Cmdlets Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="64d19-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
