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
description: Revise as respostas para perguntas frequentes sobre a implantação centralizada no centro de administração do Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948683"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="8722b-103">Perguntas frequentes sobre a Implantação centralizada</span><span class="sxs-lookup"><span data-stu-id="8722b-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="8722b-104">A implantação centralizada é a maneira recomendada para o administrador do Office 365 implantar suplementos do Office (Word, Excel, PowerPoint e Outlook) para usuários e grupos em uma organização, desde que a organização atenda a todos os requisitos para usar a implantação centralizada, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="8722b-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="8722b-105">Como saber se minha organização está configurada para implantação centralizada?</span><span class="sxs-lookup"><span data-stu-id="8722b-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="8722b-106">A implantação centralizada de suplementos requer que os usuários estejam usando o Microsoft 365 aplicativos para empresas (e estejam conectados ao Office usando suas credenciais de login organizacionais) e tenham caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8722b-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="8722b-107">O diretório de assinatura deve estar no Azure Active Directory ou federado a ele.</span><span class="sxs-lookup"><span data-stu-id="8722b-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="8722b-108">A implantação centralizada só é suportada para caixas de correio online.</span><span class="sxs-lookup"><span data-stu-id="8722b-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="8722b-109">Ele não oferece suporte à implantação em caixas de correio locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="8722b-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="8722b-110">Você pode usar o [Verificador de compatibilidade de implantação centralizado](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   para determinar se sua assinatura está qualificada.</span><span class="sxs-lookup"><span data-stu-id="8722b-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="8722b-111">Como você direciona as atribuições de usuário de suplemento com a implantação centralizada?</span><span class="sxs-lookup"><span data-stu-id="8722b-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="8722b-112">A implantação centralizada oferece suporte a atribuições para usuários individuais, grupos e todos no locatário.</span><span class="sxs-lookup"><span data-stu-id="8722b-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="8722b-113">A implantação centralizada pode ser usada para usuários em grupos de nível superior ou grupos sem grupos pai, mas não para usuários em grupos aninhados ou grupos com grupos pai.</span><span class="sxs-lookup"><span data-stu-id="8722b-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="8722b-114">A implantação centralizada também faz parte da maioria dos grupos do Active Directory do Azure, incluindo grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="8722b-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="8722b-115">É melhor usar atribuições de grupos em vez de atribuição de usuário individual para facilitar o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="8722b-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="8722b-116">Para obter mais detalhes, consulte [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="8722b-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="8722b-117">Quanto tempo leva para que suplementos sejam mostrados para todos os usuários?</span><span class="sxs-lookup"><span data-stu-id="8722b-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="8722b-118">Pode levar até 24 horas para que um suplemento seja exibido para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="8722b-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="8722b-119">Pode levar a mesma quantidade de tempo para atualizações de suplemento, alterações de ativar ou desativar ou de remoções de suplemento.</span><span class="sxs-lookup"><span data-stu-id="8722b-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="8722b-120">Como administrador, como gerenciar o acesso do usuário aos suplementos da minha organização?</span><span class="sxs-lookup"><span data-stu-id="8722b-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="8722b-121">Para facilitar a implantação de suplementos para usuários, grupos ou para toda a sua organização, recomendamos que os administradores usem a implantação centralizada.</span><span class="sxs-lookup"><span data-stu-id="8722b-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="8722b-122">Para obter mais informações sobre como gerenciar o acesso do usuário, consulte:</span><span class="sxs-lookup"><span data-stu-id="8722b-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="8722b-123">Impedir downloads de suplementos desativando a Office Store em todos os clientes (exceto Outlook)</span><span class="sxs-lookup"><span data-stu-id="8722b-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="8722b-124">Especificar os administradores e usuários que podem instalar e gerenciar aplicativos para o Outlook</span><span class="sxs-lookup"><span data-stu-id="8722b-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="8722b-125">A implantação centralizada oferece aos administradores a flexibilidade para escolher o método de implantação para os suplementos do Outlook?</span><span class="sxs-lookup"><span data-stu-id="8722b-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="8722b-126">Sim.</span><span class="sxs-lookup"><span data-stu-id="8722b-126">Yes.</span></span> <span data-ttu-id="8722b-127">A implantação centralizada oferece aos administradores a flexibilidade para escolher um dos três métodos de implantação para suplementos do Outlook durante a implantação do suplemento:</span><span class="sxs-lookup"><span data-stu-id="8722b-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="8722b-128">**Fixo (padrão)**   O suplemento é implantado automaticamente para os usuários atribuídos e não é possível removê-lo.</span><span class="sxs-lookup"><span data-stu-id="8722b-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="8722b-129">**Disponível** Os usuários podem instalar o suplemento no Outlook escolhendo **Home > obter mais suplementos > administração gerenciada**.</span><span class="sxs-lookup"><span data-stu-id="8722b-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="8722b-130">**Opcional** O suplemento é implantado automaticamente para os usuários atribuídos, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="8722b-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="8722b-131">Os administradores podem atualizar suplementos de linha de negócios (LOB)?</span><span class="sxs-lookup"><span data-stu-id="8722b-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="8722b-132">Sim.</span><span class="sxs-lookup"><span data-stu-id="8722b-132">Yes.</span></span> <span data-ttu-id="8722b-133">Os administradores podem carregar um novo arquivo de manifesto para dar suporte às alterações de metadados para suplementos LOB implantados pelo administrador. O suplemento é atualizado na próxima vez que os aplicativos do Office são iniciados.</span><span class="sxs-lookup"><span data-stu-id="8722b-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="8722b-134">O aplicativo Web pode mudar a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8722b-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="8722b-135">Para obter mais informações, consulte [suplemento de linha de negócios](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="8722b-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="8722b-136">Os administradores podem desativar os suplementos?</span><span class="sxs-lookup"><span data-stu-id="8722b-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="8722b-137">Sim.</span><span class="sxs-lookup"><span data-stu-id="8722b-137">Yes.</span></span> <span data-ttu-id="8722b-138">Os administradores podem ativar ou desativar os suplementos implantados para todos os usuários do centro de administração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8722b-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="8722b-139">Para mais informações, confira [Estados de suplementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="8722b-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="8722b-140">Os administradores podem excluir ou remover suplementos?</span><span class="sxs-lookup"><span data-stu-id="8722b-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="8722b-141">Sim.</span><span class="sxs-lookup"><span data-stu-id="8722b-141">Yes.</span></span> <span data-ttu-id="8722b-142">Os administradores podem excluir os suplementos implantados para todos os usuários do centro de administração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8722b-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="8722b-143">Para obter mais informações, consulte [excluir um suplemento](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="8722b-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="8722b-144">Os administradores podem implantar os suplementos pagos da Office Store usando a implantação centralizada?</span><span class="sxs-lookup"><span data-stu-id="8722b-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="8722b-145">Não.</span><span class="sxs-lookup"><span data-stu-id="8722b-145">No.</span></span> <span data-ttu-id="8722b-146">Você não pode implantar os suplementos pagos da Office Store usando a implantação centralizada no momento.</span><span class="sxs-lookup"><span data-stu-id="8722b-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="8722b-147">Sugerimos acessar o desenvolvedor de ISV do suplemento pago para solicitar um arquivo de manifesto ou uma URL.</span><span class="sxs-lookup"><span data-stu-id="8722b-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="8722b-148">O administrador de locatários pode implantar o suplemento como um suplemento de LOB usando a implantação centralizada.</span><span class="sxs-lookup"><span data-stu-id="8722b-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="8722b-149">Qual função de administrador preciso gerenciar suplementos para minha organização?</span><span class="sxs-lookup"><span data-stu-id="8722b-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="8722b-150">O administrador global é a função recomendada com acesso completo ao ciclo de vida de gerenciamento de suplementos.</span><span class="sxs-lookup"><span data-stu-id="8722b-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="8722b-151">Outras funções de administrador têm acesso limitado ao ciclo de vida de implantação de suplementos.</span><span class="sxs-lookup"><span data-stu-id="8722b-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="8722b-152">Se você é a pessoa que comprou sua assinatura do Microsoft 365 for Business, você é o administrador global.</span><span class="sxs-lookup"><span data-stu-id="8722b-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="8722b-153">Sua assinatura vem com um conjunto de funções de administrador que você pode atribuir a outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8722b-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="8722b-154">Cada função de administrador mapeia para funções comuns de negócios e dá às pessoas de suas permissões de organização a execução de tarefas específicas no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8722b-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="8722b-155">Para obter mais informações, consulte [assign admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8722b-155">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  


