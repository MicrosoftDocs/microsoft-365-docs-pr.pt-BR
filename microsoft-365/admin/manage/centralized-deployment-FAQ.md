---
title: Perguntas frequentes sobre a Implantação centralizada
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise as respostas para perguntas frequentes sobre Implantação Centralizada do Centro de administração do Microsoft 365.
ms.openlocfilehash: 9f4841508701d4dd5878e99fcc51a436bc5824e2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915465"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="4114c-103">Perguntas frequentes sobre a Implantação centralizada</span><span class="sxs-lookup"><span data-stu-id="4114c-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="4114c-104">A Implantação Centralizada é a maneira recomendada para um administrador do Office 365 implantar os complementos do Office (Word, Excel, PowerPoint e Outlook) para usuários e grupos dentro de uma organização, desde que a organização atenda a todos os requisitos para usar a Implantação Centralizada conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4114c-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="4114c-105">Como saber se minha organização está configurada para Implantação Centralizada?</span><span class="sxs-lookup"><span data-stu-id="4114c-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="4114c-106">A implantação centralizada de complementos exige que os usuários estão usando o Microsoft 365 Apps para empresas (e são assinados no Office usando suas credenciais de logoff organizacionais) e têm caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4114c-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="4114c-107">Seu diretório de assinatura deve estar no Azure Active Directory ou federado.</span><span class="sxs-lookup"><span data-stu-id="4114c-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="4114c-108">A Implantação Centralizada só é suportada para caixas de correio online.</span><span class="sxs-lookup"><span data-stu-id="4114c-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="4114c-109">Ele não dá suporte à implantação para caixas de correio locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4114c-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="4114c-110">Você pode usar o [Verificador de Compatibilidade](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)de Implantação Centralizado   para determinar se sua assinatura está qualificada.</span><span class="sxs-lookup"><span data-stu-id="4114c-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="4114c-111">Como você direciona as atribuições de usuário do complemento com a Implantação Centralizada?</span><span class="sxs-lookup"><span data-stu-id="4114c-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="4114c-112">A Implantação Centralizada dá suporte a atribuições para usuários individuais, grupos e todos no locatário.</span><span class="sxs-lookup"><span data-stu-id="4114c-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="4114c-113">A Implantação Centralizada pode ser usada para usuários em grupos de nível superior ou grupos sem grupos pai, mas não para usuários em grupos aninhados ou grupos que têm grupos pai.</span><span class="sxs-lookup"><span data-stu-id="4114c-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="4114c-114">A Implantação Centralizada também faz parte da maioria dos grupos do Azure Active Directory, incluindo grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="4114c-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="4114c-115">É melhor usar atribuições de grupos em vez de atribuição de usuário individual para facilitar o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4114c-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="4114c-116">Para obter mais detalhes, consulte [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="4114c-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="4114c-117">Quanto tempo leva para os complementos aparecerem para todos os usuários?</span><span class="sxs-lookup"><span data-stu-id="4114c-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="4114c-118">Pode levar até 24 horas para um complemento aparecer para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="4114c-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="4114c-119">Pode levar o mesmo tempo para atualizações de complementos, alterações de ativar ou desativar ou remoção de complementos.</span><span class="sxs-lookup"><span data-stu-id="4114c-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="4114c-120">Como administrador, como gerencio o acesso do usuário aos complementos da minha organização?</span><span class="sxs-lookup"><span data-stu-id="4114c-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="4114c-121">Para facilitar a implantação de complementos para usuários, grupos ou para toda a sua organização, recomendamos que os administradores usem a Implantação Centralizada.</span><span class="sxs-lookup"><span data-stu-id="4114c-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="4114c-122">Para obter mais informações sobre como gerenciar o acesso do usuário, consulte:</span><span class="sxs-lookup"><span data-stu-id="4114c-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="4114c-123">Impedir downloads de complementos ao desligar a Office Store em todos os clientes (exceto o Outlook)</span><span class="sxs-lookup"><span data-stu-id="4114c-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="4114c-124">Especificar os administradores e usuários que podem instalar e gerenciar aplicativos para o Outlook</span><span class="sxs-lookup"><span data-stu-id="4114c-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="4114c-125">A Implantação Centralizada fornecerá aos administradores a flexibilidade para escolher o método de implantação para os complementos do Outlook?</span><span class="sxs-lookup"><span data-stu-id="4114c-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="4114c-126">Sim.</span><span class="sxs-lookup"><span data-stu-id="4114c-126">Yes.</span></span> <span data-ttu-id="4114c-127">A Implantação Centralizada oferece aos administradores a flexibilidade de escolher um dos três métodos de implantação para os complementos do Outlook durante a implantação do complemento:</span><span class="sxs-lookup"><span data-stu-id="4114c-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="4114c-128">**Fixo (Padrão)**   O complemento é implantado automaticamente para os usuários atribuídos, e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="4114c-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="4114c-129">**Disponível** Os usuários podem instalar o add-in no Outlook escolhendo **Home > Obter mais > admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="4114c-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="4114c-130">**Opcional** O complemento é implantado automaticamente para os usuários atribuídos, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="4114c-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="4114c-131">Os administradores podem atualizar os complementos de Linha de Negócios (LOB)?</span><span class="sxs-lookup"><span data-stu-id="4114c-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="4114c-132">Sim.</span><span class="sxs-lookup"><span data-stu-id="4114c-132">Yes.</span></span> <span data-ttu-id="4114c-133">Os administradores podem carregar um novo arquivo de manifesto para dar suporte a alterações de metadados para os complementos LOB implantados pelo administrador. O complemento é atualizado na próxima vez que os aplicativos do Office são iniciados.</span><span class="sxs-lookup"><span data-stu-id="4114c-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="4114c-134">O aplicativo Web pode mudar a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="4114c-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="4114c-135">Para obter mais informações, consulte [line-of-business add-in](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="4114c-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="4114c-136">Os administradores podem desativar os complementos?</span><span class="sxs-lookup"><span data-stu-id="4114c-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="4114c-137">Sim.</span><span class="sxs-lookup"><span data-stu-id="4114c-137">Yes.</span></span> <span data-ttu-id="4114c-138">Os administradores podem ativar ou desativar os complementos implantados para todos os usuários do centro de administração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4114c-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="4114c-139">Para obter mais informações, consulte [Estados de complemento](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="4114c-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="4114c-140">Os administradores podem excluir ou remover os complementos?</span><span class="sxs-lookup"><span data-stu-id="4114c-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="4114c-141">Sim.</span><span class="sxs-lookup"><span data-stu-id="4114c-141">Yes.</span></span> <span data-ttu-id="4114c-142">Os administradores podem excluir os complementos implantados para todos os usuários do centro de administração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4114c-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="4114c-143">Para obter mais informações, consulte [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="4114c-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="4114c-144">Os administradores podem implantar os complementos pagos da Office Store usando a Implantação Centralizada?</span><span class="sxs-lookup"><span data-stu-id="4114c-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="4114c-145">Não.</span><span class="sxs-lookup"><span data-stu-id="4114c-145">No.</span></span> <span data-ttu-id="4114c-146">Não é possível implantar os complementos pagos da Office Store usando a Implantação Centralizada no momento.</span><span class="sxs-lookup"><span data-stu-id="4114c-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="4114c-147">Sugerimos entrar em ação com o Desenvolvedor ISV para que o complemento pago solicite um arquivo de manifesto ou uma URL.</span><span class="sxs-lookup"><span data-stu-id="4114c-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="4114c-148">Em seguida, o administrador do locatário pode implantar o add-in como um complemento LOB usando a Implantação Centralizada.</span><span class="sxs-lookup"><span data-stu-id="4114c-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="4114c-149">Qual função de administrador preciso gerenciar os complementos para minha organização?</span><span class="sxs-lookup"><span data-stu-id="4114c-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="4114c-150">Administrador Global é a função recomendada com acesso completo ao ciclo de vida de gerenciamento de complementos.</span><span class="sxs-lookup"><span data-stu-id="4114c-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="4114c-151">Outras funções de administrador têm acesso limitado ao ciclo de vida de implantação do complemento.</span><span class="sxs-lookup"><span data-stu-id="4114c-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="4114c-152">Se você for a pessoa que comprou sua assinatura do Microsoft 365 para empresas, você será o administrador global.</span><span class="sxs-lookup"><span data-stu-id="4114c-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="4114c-153">Sua assinatura vem com um conjunto de funções de administrador que você pode atribuir a outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4114c-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="4114c-154">Cada função de administrador mapeia para funções comerciais comuns e dá às pessoas em sua organização permissões para executar tarefas específicas no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4114c-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="4114c-155">Para obter mais informações, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4114c-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 