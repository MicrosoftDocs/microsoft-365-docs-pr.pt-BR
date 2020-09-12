---
title: Políticas de acesso de dispositivo e identidade para permitir acesso B2B e de convidado externo-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve o acesso condicional recomendado e as políticas relacionadas para proteger o acesso de usuários externos e convidados.
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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546461"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="365d2-103">Políticas para permitir acesso B2B e de convidado externo</span><span class="sxs-lookup"><span data-stu-id="365d2-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="365d2-104">Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir acesso à conta de B2B (entre empresas) (usuários convidados e externos).</span><span class="sxs-lookup"><span data-stu-id="365d2-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="365d2-105">Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="365d2-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="365d2-106">Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção.</span><span class="sxs-lookup"><span data-stu-id="365d2-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="365d2-107">No entanto, você também pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** .</span><span class="sxs-lookup"><span data-stu-id="365d2-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="365d2-108">Fornecer um caminho para que os usuários B2B autentiquem com seu locatário do Azure Active Directory (Azure AD) não concede a esses usuários acesso a todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="365d2-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="365d2-109">Os usuários B2B têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos nas políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="365d2-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="365d2-110">Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados</span><span class="sxs-lookup"><span data-stu-id="365d2-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="365d2-111">Para proteger o acesso externo e de convidados, o diagrama a seguir ilustra quais políticas serão adicionadas ou atualizadas das políticas comuns de acesso de identidade e de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="365d2-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="365d2-112">[![Resumo das atualizações de política para proteger o acesso de convidados](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="365d2-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="365d2-113">Veja uma versão maior desta imagem</span><span class="sxs-lookup"><span data-stu-id="365d2-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="365d2-114">A tabela a seguir lista as políticas que você precisa atualizar ou criar novas.</span><span class="sxs-lookup"><span data-stu-id="365d2-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="365d2-115">O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="365d2-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="365d2-116">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="365d2-116">Protection level</span></span>|<span data-ttu-id="365d2-117">Políticas</span><span class="sxs-lookup"><span data-stu-id="365d2-117">Policies</span></span>|<span data-ttu-id="365d2-118">Mais informações</span><span class="sxs-lookup"><span data-stu-id="365d2-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="365d2-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="365d2-119">**Baseline**</span></span>|[<span data-ttu-id="365d2-120">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="365d2-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="365d2-121">Crie essa nova política e aplique-a somente a convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="365d2-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="365d2-122">Em **risco de entrada**, deixe todas as opções desmarcadas para sempre impor a autenticação multifator (MFA).</span><span class="sxs-lookup"><span data-stu-id="365d2-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="365d2-123">Exigir MFA quando o risco de entrada for *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="365d2-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="365d2-124">Modifique esta política para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="365d2-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="365d2-125">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="365d2-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="365d2-126">Modifique esta política para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="365d2-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="365d2-127">Para incluir ou excluir convidados e usuários externos em políticas de acesso condicional, clique na guia **incluir** ou **excluir** e marque **todos os convidados e usuários externos**.</span><span class="sxs-lookup"><span data-stu-id="365d2-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![captura de tela de controles para excluir convidados](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="365d2-129">Mais informações</span><span class="sxs-lookup"><span data-stu-id="365d2-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="365d2-130">Convidados vs. usuários externos</span><span class="sxs-lookup"><span data-stu-id="365d2-130">Guests vs. external users</span></span>
<span data-ttu-id="365d2-131">No Azure AD, os usuários convidados e externos são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="365d2-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="365d2-132">O tipo de usuário para ambos é Guest.</span><span class="sxs-lookup"><span data-stu-id="365d2-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="365d2-133">Os usuários convidados são usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="365d2-133">Guest users are B2B users.</span></span>

<span data-ttu-id="365d2-134">O Microsoft Teams diferencia entre usuários convidados e usuários externos dentro do aplicativo, mas são usuários de B2B durante a autenticação.</span><span class="sxs-lookup"><span data-stu-id="365d2-134">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="365d2-135">Para obter mais informações sobre os usuários convidados e externos do Teams, consulte [habilitar o convidado e o acesso externo para o Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="365d2-135">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="365d2-136">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="365d2-136">Require MFA always for guest and external users</span></span>
<span data-ttu-id="365d2-137">Essa política solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para MFA em seu locatário de casa.</span><span class="sxs-lookup"><span data-stu-id="365d2-137">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="365d2-138">Ao acessar recursos em seu locatário, convidados e usuários externos precisam usar a MFA para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="365d2-138">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="365d2-139">Excluindo usuários convidados e externos da MFA baseada em riscos</span><span class="sxs-lookup"><span data-stu-id="365d2-139">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="365d2-140">Enquanto as organizações podem reforçar políticas com base em risco para usuários B2B usando a proteção de identidade do Azure AD, há limitações na implementação da proteção de identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base.</span><span class="sxs-lookup"><span data-stu-id="365d2-140">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="365d2-141">Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA.</span><span class="sxs-lookup"><span data-stu-id="365d2-141">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="365d2-142">Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="365d2-142">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="365d2-143">Excluindo usuários convidados e externos do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="365d2-143">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="365d2-144">Somente uma organização pode gerenciar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="365d2-144">Only one organization can manage a device.</span></span> <span data-ttu-id="365d2-145">Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários.</span><span class="sxs-lookup"><span data-stu-id="365d2-145">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="365d2-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="365d2-146">Next step</span></span>

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="365d2-148">Configure as políticas de acesso condicional para:</span><span class="sxs-lookup"><span data-stu-id="365d2-148">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="365d2-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="365d2-149">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="365d2-150">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="365d2-150">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="365d2-151">SharePoint</span><span class="sxs-lookup"><span data-stu-id="365d2-151">SharePoint</span></span>](secure-email-recommended-policies.md)

