---
title: 'Etapa 1: Planeje para usuários e grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planeje para o conjunto de usuários e grupos que trabalharão para sua organização.
ms.openlocfilehash: ac7f5e56bae882e01c31cacee856f73b0ead772f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071630"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="8d93f-103">Etapa 1: Planeje para usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="8d93f-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="8d93f-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8d93f-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8d93f-p101">Nesta etapa, você criará sua infraestrutura de identidade que combina usuários, grupos e associações a grupos com recursos de segurança na configuração correta. Isso permite que você:</span><span class="sxs-lookup"><span data-stu-id="8d93f-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="8d93f-107">Mantenha o controle sobre quem tem acesso aos recursos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="8d93f-108">Proteja o acesso com controles que garantem a identidade (os usuários são quem dizem ser) e o acesso de dispositivos seguros.</span><span class="sxs-lookup"><span data-stu-id="8d93f-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="8d93f-109">Provisione recursos em seu ambiente com permissões apropriadas para reduzir o potencial para danos e vazamento de dados.</span><span class="sxs-lookup"><span data-stu-id="8d93f-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="8d93f-110">Monitore seu ambiente para identificar comportamentos anômalos de usuários e agir automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="8d93f-111">Planejar seu provedor de identidade principal</span><span class="sxs-lookup"><span data-stu-id="8d93f-111">Plan your primary identity provider</span></span>

<span data-ttu-id="8d93f-p102">Para criar sua infraestrutura de identidade, você designará um provedor de identidade principal. Esse serviço armazena contas de usuário e seus atributos, grupos e seus membros e oferece suporte para sua administração contínua.</span><span class="sxs-lookup"><span data-stu-id="8d93f-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="8d93f-114">Quando sua organização adotar o Microsoft 365 Enterprise, seu provedor de identidade principal será:</span><span class="sxs-lookup"><span data-stu-id="8d93f-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="8d93f-115">**Serviços de Domínio do Active Directory (AD DS)**, um provedor de identidade intranet hospedado em computadores que executam o Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8d93f-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="8d93f-116">Ele normalmente é usado por empresas que têm um provedor de identidade local existente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="8d93f-117">**Azure Active Directory (Azure AD)**, uma identidade como um serviço baseada em nuvem (IDaaS) que oferece uma ampla variedade de recursos para gerenciar e proteger o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="8d93f-118">Ele normalmente é usado por empresas que não têm uma infraestrutura local existente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="8d93f-119">Se sua organização tiver um provedor de identidade local existente, é necessário sincronizar suas contas de usuários e grupos do AD DS ao Azure AD para fornecer acesso mais contínuo aos serviços baseados em nuvem do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8d93f-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from AD DS to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="8d93f-120">Você também pode usar o Azure AD para criar e gerenciar grupos que existam somente na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d93f-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="8d93f-121">Quando você tiver seus usuários e grupos no Azure AD, você poderá:</span><span class="sxs-lookup"><span data-stu-id="8d93f-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="8d93f-122">Gerenciar todas as contas do Azure AD para todos os aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8d93f-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="8d93f-123">Usar o mesmo conjunto de controles para proteger o acesso a aplicativos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="8d93f-124">Colaborar com parceiros externos.</span><span class="sxs-lookup"><span data-stu-id="8d93f-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="8d93f-125">Monitorar comportamentos de contas anômalos, como tentativas suspeitas de login, e tomar medidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8d93f-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="8d93f-126">Siga as instruções nas próximas duas seções para planejar e implementar suas contas e grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="8d93f-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="8d93f-127">Categorizar seus usuários</span><span class="sxs-lookup"><span data-stu-id="8d93f-127">Categorize your users</span></span>
<span data-ttu-id="8d93f-p106">Os usuários em organizações podem ser categorizados de várias maneiras. Por exemplo, alguns são funcionários e têm status permanente. Alguns são fornecedores, prestadores de serviços ou parceiros que têm status temporário. Alguns são usuários externos que não têm contas de usuário, mas que ainda devem ter acesso a recursos e serviços específicos para permitir a interação e colaboração. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8d93f-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="8d93f-133">As contas do locatário representam os usuários em sua organização para os quais você atribui uma licença para os serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="8d93f-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="8d93f-134">As contas entre empresas (B2B) representam usuários de fora da sua organização que você convida para colaborar</span><span class="sxs-lookup"><span data-stu-id="8d93f-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="8d93f-p107">Analise os tipos de usuários em sua organização. Quais são os grupos? Por exemplo, você pode agrupar usuários por função ou propósito geral em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8d93f-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="8d93f-p108">Além disso, alguns serviços de nuvem podem ser compartilhados com usuários de fora de sua organização que não tenham contas de usuário. Você também precisará identificar esses grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="8d93f-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="8d93f-140">Planejar grupos do AD DS e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8d93f-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="8d93f-p109">Você pode usar grupos no Azure AD para várias finalidades que simplifiquem o gerenciamento de seu ambiente de nuvem. Por exemplo, para grupos do Azure AD, você pode:</span><span class="sxs-lookup"><span data-stu-id="8d93f-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="8d93f-143">Usar o licenciamento baseado em grupo para atribuir licenças às suas contas de usuário automaticamente assim que elas forem adicionadas ao Azure AD ou sincronizadas do AD DS.</span><span class="sxs-lookup"><span data-stu-id="8d93f-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="8d93f-144">Adicionar contas de usuário a grupos específicos de modo dinâmico com base em atributos das contas de usuário, como o departamento.</span><span class="sxs-lookup"><span data-stu-id="8d93f-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="8d93f-145">Provisionar usuários automaticamente para aplicativos de Software como um Serviço (SaaS) e para proteger o acesso a esses aplicativos com a autenticação multifator e outras regras de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="8d93f-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="8d93f-p110">Provisionar permissões e níveis de acesso para sites de equipe do SharePoint Online. Grupos do Azure AD também podem ser usados com confidencialidade ou rótulos de Proteção de Informações do Azure para proteger os arquivos com criptografia e permissões.</span><span class="sxs-lookup"><span data-stu-id="8d93f-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="8d93f-148">Resultados</span><span class="sxs-lookup"><span data-stu-id="8d93f-148">Results</span></span>

<span data-ttu-id="8d93f-149">Ao concluir esta etapa, você terá:</span><span class="sxs-lookup"><span data-stu-id="8d93f-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="8d93f-150">Uma lista de contas de usuário no Azure AD que correspondem aos funcionários da sua organização e aos fornecedores, prestadores de serviços e parceiros externos que trabalham para ou com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="8d93f-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="8d93f-151">Um conjunto de grupos e seus membros no Azure AD que refletem conjuntos lógicos de contas de usuário e outros grupos para o provisionamento automático de licenciamento para as configurações de segurança para os serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d93f-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="8d93f-152">Quando seus usuários e grupos do Azure AD forem criados, você poderá começar a atribuir licenças e a usar cargas de trabalho de produtividade como o OneDrive for Business ou o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d93f-152">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d93f-153">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8d93f-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="8d93f-154">Proteger suas identidades privilegiadas</span><span class="sxs-lookup"><span data-stu-id="8d93f-154">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

