---
title: Políticas de acesso de dispositivo e identidade para permitir acesso B2B de usuários convidados e externos - Microsoft 365 para empresas | Microsoft Docs
description: Descreve o Acesso Condicional recomendado e políticas relacionadas para proteger o acesso de convidados e usuários externos.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 4ce52c40e622f55b0fd231ec634c4897fea1d6f5
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615490"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="c3c57-103">Políticas para permitir acesso de convidados e acesso de usuário externo B2B</span><span class="sxs-lookup"><span data-stu-id="c3c57-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="c3c57-104">Este artigo aborda o ajuste das políticas recomendadas de acesso a dispositivos e identidades para permitir o acesso a convidados e usuários externos que tenham uma conta do Azure Active Directory (Azure AD) Business-to-Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="c3c57-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="c3c57-105">Essa orientação se baseia nas políticas [comuns de identidade e acesso a dispositivos.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c3c57-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="c3c57-106">Essas recomendações foram projetadas para se aplicar à camada **de linha** de base de proteção.</span><span class="sxs-lookup"><span data-stu-id="c3c57-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="c3c57-107">Mas você também pode ajustar as recomendações com base em suas necessidades específicas para **proteção** sensível **e altamente regulamentada.**</span><span class="sxs-lookup"><span data-stu-id="c3c57-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="c3c57-108">Fornecer um caminho para contas B2B autenticar com seu locatário do Azure AD não dá a essas contas acesso a todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3c57-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="c3c57-109">Os usuários B2B e suas contas têm acesso a serviços e recursos, como arquivos, compartilhados com eles pela política de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="c3c57-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="c3c57-110">Atualizando as políticas comuns para permitir e proteger convidados e acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="c3c57-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="c3c57-111">Este diagrama mostra quais políticas adicionar ou atualizar entre as políticas comuns de acesso a dispositivos e identidade, para acesso de usuário externo e convidado B2B.</span><span class="sxs-lookup"><span data-stu-id="c3c57-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="c3c57-112">[![Resumo das atualizações de política para proteger o acesso de convidados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="c3c57-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="c3c57-113">A tabela a seguir lista as políticas que você precisa criar e atualizar.</span><span class="sxs-lookup"><span data-stu-id="c3c57-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="c3c57-114">As políticas comuns vinculam-se às instruções de configuração associadas no [artigo Common identity and device access policies.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c3c57-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="c3c57-115">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="c3c57-115">Protection level</span></span>|<span data-ttu-id="c3c57-116">Políticas</span><span class="sxs-lookup"><span data-stu-id="c3c57-116">Policies</span></span>|<span data-ttu-id="c3c57-117">Mais informações</span><span class="sxs-lookup"><span data-stu-id="c3c57-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="c3c57-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="c3c57-118">**Baseline**</span></span>|[<span data-ttu-id="c3c57-119">Exigir MFA sempre para convidados e usuários externos</span><span class="sxs-lookup"><span data-stu-id="c3c57-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c3c57-120">Crie essa nova política e configure:</span><span class="sxs-lookup"><span data-stu-id="c3c57-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="c3c57-121">Para **atribuições > Usuários** e grupos > Incluir , escolha **Selecionar** usuários e grupos e selecione Todos os usuários convidados **e externos**.</span><span class="sxs-lookup"><span data-stu-id="c3c57-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="c3c57-122">Para **Atribuições > Condições > Entrar,** deixe todas as opções desmarcadas para sempre impor a autenticação multifatória (MFA).</span><span class="sxs-lookup"><span data-stu-id="c3c57-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="c3c57-123">Exigir MFA quando o risco de entrar é *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="c3c57-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c3c57-124">Modifique essa política para excluir convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c3c57-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="c3c57-125">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="c3c57-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="c3c57-126">Modifique essa política para excluir convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c3c57-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="c3c57-127">Para incluir ou excluir convidados e usuários externos em políticas de Acesso Condicional, para atribuições > Usuários e grupos > Incluir ou Excluir **,** verifique Todos os usuários convidados e **externos.** </span><span class="sxs-lookup"><span data-stu-id="c3c57-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de tela de controles para excluir convidados e usuários externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="c3c57-129">Mais informações</span><span class="sxs-lookup"><span data-stu-id="c3c57-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="c3c57-130">Convidados e acesso de usuário externo com Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3c57-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="c3c57-131">Microsoft Teams define os seguintes usuários:</span><span class="sxs-lookup"><span data-stu-id="c3c57-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="c3c57-132">**O acesso de** convidados usa uma conta B2B do Azure AD que pode ser adicionada como membro de uma equipe e ter acesso às comunicações e recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="c3c57-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="c3c57-133">**O acesso** externo é para um usuário externo que não tem uma conta B2B.</span><span class="sxs-lookup"><span data-stu-id="c3c57-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="c3c57-134">O acesso de usuário externo inclui convites, chamadas, chats e reuniões, mas não inclui a associação à equipe e o acesso aos recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="c3c57-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="c3c57-135">Para obter mais informações, consulte a [comparação entre convidados e acesso de usuário externo para equipes](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="c3c57-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="c3c57-136">Para obter mais informações sobre como proteger políticas de identidade e acesso a dispositivos para Teams, consulte Recomendações de política para proteger Teams [chats,](teams-access-policies.md)grupos e arquivos.</span><span class="sxs-lookup"><span data-stu-id="c3c57-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="c3c57-137">Exigir MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="c3c57-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="c3c57-138">Esta política solicita que os convidados se registrem no MFA em seu locatário, independentemente de eles estar registrados para MFA em seu locatário ínteco.</span><span class="sxs-lookup"><span data-stu-id="c3c57-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="c3c57-139">Ao acessar recursos em seu locatário, os convidados e os usuários externos devem usar o MFA para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="c3c57-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="c3c57-140">Excluindo convidados e usuários externos do MFA baseado em risco</span><span class="sxs-lookup"><span data-stu-id="c3c57-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="c3c57-141">Embora as organizações possam impor políticas baseadas em risco para usuários B2B usando a Proteção de Identidade do Azure AD, há limitações na implementação da Proteção de Identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório inicial.</span><span class="sxs-lookup"><span data-stu-id="c3c57-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="c3c57-142">Devido a essas limitações, a Microsoft recomenda excluir convidados de políticas MFA baseadas em risco e exigir que esses usuários sempre usem mFA.</span><span class="sxs-lookup"><span data-stu-id="c3c57-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="c3c57-143">Para obter mais informações, consulte [Limitações da Proteção de Identidade para usuários de colaboração B2B.](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="c3c57-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="c3c57-144">Excluindo convidados e usuários externos do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3c57-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="c3c57-145">Somente uma organização pode gerenciar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3c57-145">Only one organization can manage a device.</span></span> <span data-ttu-id="c3c57-146">Se você não excluir convidados e usuários externos de políticas que exigem conformidade com o dispositivo, essas políticas bloquearão esses usuários.</span><span class="sxs-lookup"><span data-stu-id="c3c57-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3c57-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c3c57-147">Next step</span></span>

![Etapa 4: Políticas para aplicativos Microsoft 365 nuvem e Microsoft Cloud App Security](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="c3c57-149">Configurar políticas de Acesso Condicional para:</span><span class="sxs-lookup"><span data-stu-id="c3c57-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="c3c57-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3c57-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="c3c57-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3c57-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="c3c57-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c3c57-152">SharePoint</span></span>](sharepoint-file-access-policies.md)
- [<span data-ttu-id="c3c57-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3c57-153">Microsoft Cloud App Security</span></span>](mcas-saas-access-policies.md)
 