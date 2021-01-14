---
title: Políticas de acesso a identidades e dispositivos para permitir acesso B2B a usuários convidados e externos - Microsoft 365 para empresas | Microsoft Docs
description: Descreve o Acesso Condicional recomendado e as políticas relacionadas para proteger o acesso de convidados e usuários externos.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845071"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="3afd5-103">Políticas para permitir acesso de convidados e acesso de usuário externo B2B</span><span class="sxs-lookup"><span data-stu-id="3afd5-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="3afd5-104">Este artigo discute o ajuste das políticas de acesso de identidade e dispositivo recomendadas para permitir o acesso a convidados e usuários externos que tenham uma conta do Azure Active Directory (Azure AD) Business para Empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="3afd5-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="3afd5-105">Essa orientação se baseia nas políticas [comuns de acesso a dispositivos e identidades.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3afd5-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="3afd5-106">Essas recomendações foram projetadas para se aplicar à camada **de linha de** base de proteção.</span><span class="sxs-lookup"><span data-stu-id="3afd5-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="3afd5-107">Mas você também pode ajustar as recomendações com base em suas necessidades específicas de **proteção altamente** **controlada e** sensível.</span><span class="sxs-lookup"><span data-stu-id="3afd5-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="3afd5-108">Fornecer um caminho para contas B2B autenticar com seu locatário do Azure AD não dá a essas contas acesso a todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3afd5-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="3afd5-109">Os usuários B2B e suas contas têm acesso a serviços e recursos, como arquivos, compartilhados com eles pela política de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="3afd5-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="3afd5-110">Atualizando as políticas comuns para permitir e proteger convidados e acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="3afd5-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="3afd5-111">Este diagrama mostra quais políticas adicionar ou atualizar entre as políticas comuns de acesso a dispositivos e identidade, para acesso de usuário externo e convidado B2B.</span><span class="sxs-lookup"><span data-stu-id="3afd5-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="3afd5-112">[![Resumo das atualizações de política para proteger o acesso de convidados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="3afd5-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="3afd5-113">Ver uma versão maior desta imagem</span><span class="sxs-lookup"><span data-stu-id="3afd5-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="3afd5-114">A tabela a seguir lista as políticas que você precisa criar e atualizar.</span><span class="sxs-lookup"><span data-stu-id="3afd5-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="3afd5-115">As políticas comuns vinculam-se às instruções de configuração associadas no artigo De identidade [comum e políticas de acesso a dispositivos.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3afd5-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="3afd5-116">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="3afd5-116">Protection level</span></span>|<span data-ttu-id="3afd5-117">Políticas</span><span class="sxs-lookup"><span data-stu-id="3afd5-117">Policies</span></span>|<span data-ttu-id="3afd5-118">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3afd5-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="3afd5-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="3afd5-119">**Baseline**</span></span>|[<span data-ttu-id="3afd5-120">Exigir MFA sempre para convidados e usuários externos</span><span class="sxs-lookup"><span data-stu-id="3afd5-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3afd5-121">Crie essa nova política e configure:</span><span class="sxs-lookup"><span data-stu-id="3afd5-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="3afd5-122">For **Assignments > Users and groups > Include**, choose Select users and **groups**, and then select All guest and **external users**.</span><span class="sxs-lookup"><span data-stu-id="3afd5-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="3afd5-123">Para **Atribuições > condições > entrar,** deixe todas as opções desmarcadas para sempre impor a autenticação multifatória (MFA).</span><span class="sxs-lookup"><span data-stu-id="3afd5-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="3afd5-124">Exigir MFA quando o risco de login for *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="3afd5-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3afd5-125">Modifique essa política para excluir convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="3afd5-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="3afd5-126">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="3afd5-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="3afd5-127">Modifique essa política para excluir convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="3afd5-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="3afd5-128">Para incluir ou excluir convidados e usuários **externos** em políticas de Acesso Condicional, para Atribuições > Usuários e grupos > Incluir ou **Excluir,** verifique todos os usuários convidados e **externos.**</span><span class="sxs-lookup"><span data-stu-id="3afd5-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de tela de controles para excluir convidados e usuários externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="3afd5-130">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3afd5-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="3afd5-131">Convidados e acesso de usuário externo com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3afd5-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="3afd5-132">O Microsoft Teams define os seguintes usuários:</span><span class="sxs-lookup"><span data-stu-id="3afd5-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="3afd5-133">**O acesso** de convidados usa uma conta B2B do Azure AD que pode ser adicionada como membro de uma equipe e ter acesso às comunicações e aos recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="3afd5-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="3afd5-134">**O acesso** externo é para um usuário externo que não tem uma conta B2B.</span><span class="sxs-lookup"><span data-stu-id="3afd5-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="3afd5-135">O acesso de usuário externo inclui convites, chamadas, chats e reuniões, mas não inclui a associação à equipe e o acesso aos recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="3afd5-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="3afd5-136">Para obter mais informações, consulte a [comparação entre convidados e o acesso de usuário externo para equipes.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="3afd5-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="3afd5-137">Para obter mais informações sobre como proteger políticas de acesso a identidades e dispositivos para o Teams, confira Recomendações de política para proteger [chats,](teams-access-policies.md)grupos e arquivos do Teams.</span><span class="sxs-lookup"><span data-stu-id="3afd5-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="3afd5-138">Exigir MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="3afd5-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="3afd5-139">Essa política solicita que os convidados se registrem para a MFA em seu locatário, independentemente de eles estar registrados para MFA em seu locatário de residência.</span><span class="sxs-lookup"><span data-stu-id="3afd5-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="3afd5-140">Ao acessar recursos em seu locatário, convidados e usuários externos devem usar a MFA para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="3afd5-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="3afd5-141">Excluindo convidados e usuários externos da MFA baseada em risco</span><span class="sxs-lookup"><span data-stu-id="3afd5-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="3afd5-142">Embora as organizações possam impor políticas baseadas em risco para usuários B2B usando o Azure AD Identity Protection, há limitações na implementação do Azure AD Identity Protection para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base.</span><span class="sxs-lookup"><span data-stu-id="3afd5-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="3afd5-143">Devido a essas limitações, a Microsoft recomenda que você exclua convidados de políticas de MFA baseadas em risco e exige que esses usuários sempre usem a MFA.</span><span class="sxs-lookup"><span data-stu-id="3afd5-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="3afd5-144">Para obter mais informações, [consulte Limitações da Proteção de Identidade para usuários de colaboração B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="3afd5-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="3afd5-145">Excluindo convidados e usuários externos do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="3afd5-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="3afd5-146">Somente uma organização pode gerenciar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3afd5-146">Only one organization can manage a device.</span></span> <span data-ttu-id="3afd5-147">Se você não excluir convidados e usuários externos de políticas que exigem conformidade do dispositivo, essas políticas bloquearão esses usuários.</span><span class="sxs-lookup"><span data-stu-id="3afd5-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="3afd5-148">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3afd5-148">Next step</span></span>

![Etapa 4: Políticas para aplicativos de nuvem do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="3afd5-150">Configurar políticas de Acesso Condicional para:</span><span class="sxs-lookup"><span data-stu-id="3afd5-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="3afd5-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3afd5-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="3afd5-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3afd5-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="3afd5-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3afd5-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
