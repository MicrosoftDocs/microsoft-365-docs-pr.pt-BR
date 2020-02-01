---
title: Políticas de acesso de dispositivo e identidade para permitir acesso B2B e de convidado externo-Microsoft 365 Enterprise | Microsoft docs
description: Descreve o acesso condicional recomendado e as políticas relacionadas para proteger o acesso de usuários externos e convidados.
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: ca9b752f55ebe3fecec4f312bc89b45d99cf0d7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601048"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="219b8-103">Políticas para permitir acesso B2B e de convidado externo</span><span class="sxs-lookup"><span data-stu-id="219b8-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="219b8-104">Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir o acesso de contas de B2B (convidados e usuários externos).</span><span class="sxs-lookup"><span data-stu-id="219b8-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="219b8-105">Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="219b8-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="219b8-106">Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção.</span><span class="sxs-lookup"><span data-stu-id="219b8-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="219b8-107">No entanto, você pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** .</span><span class="sxs-lookup"><span data-stu-id="219b8-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="219b8-108">O fornecimento de um caminho para que os usuários B2B autentiquem com seu locatário do Azure AD não concede a esses usuários acesso a todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="219b8-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="219b8-109">Os usuários B2B têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos nas políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="219b8-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="219b8-110">Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados</span><span class="sxs-lookup"><span data-stu-id="219b8-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="219b8-111">O diagrama a seguir ilustra as políticas comuns de acesso de dispositivo e identidades e indica (com um ícone de lápis) quais políticas serão adicionadas ou atualizadas para proteger o acesso externo e convidado.</span><span class="sxs-lookup"><span data-stu-id="219b8-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![Resumo das atualizações de política para proteger o acesso de convidados](../images/identity-access-ruleset-guest.png)

<span data-ttu-id="219b8-113">A tabela a seguir lista as políticas que você precisa atualizar ou criar novas.</span><span class="sxs-lookup"><span data-stu-id="219b8-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="219b8-114">O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="219b8-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="219b8-115">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="219b8-115">Protection level</span></span>|<span data-ttu-id="219b8-116">Políticas</span><span class="sxs-lookup"><span data-stu-id="219b8-116">Policies</span></span>|<span data-ttu-id="219b8-117">Mais informações</span><span class="sxs-lookup"><span data-stu-id="219b8-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="219b8-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="219b8-118">**Baseline**</span></span>|[<span data-ttu-id="219b8-119">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="219b8-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="219b8-120">Crie essa nova regra e aplique-a somente a convidados e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="219b8-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="219b8-121">Em risco de entrada, deixe todas as opções desmarcadas para sempre impor a MFA.</span><span class="sxs-lookup"><span data-stu-id="219b8-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="219b8-122">Exigir MFA quando o risco de entrada for *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="219b8-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="219b8-123">Modifique esta regra para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="219b8-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="219b8-124">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="219b8-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="219b8-125">Modifique esta regra para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="219b8-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="219b8-126">Para incluir ou excluir convidados e usuários externos nas regras de acesso condicional, clique na guia incluir ou excluir e marque **todos os convidados e usuários externos**.</span><span class="sxs-lookup"><span data-stu-id="219b8-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![captura de tela de controles para excluir convidados](../images/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="219b8-128">Mais informações</span><span class="sxs-lookup"><span data-stu-id="219b8-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="219b8-129">Convidados vs. usuários externos</span><span class="sxs-lookup"><span data-stu-id="219b8-129">Guests vs. external users</span></span>
<span data-ttu-id="219b8-130">No Azure AD, os usuários convidados e externos são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="219b8-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="219b8-131">O tipo de usuário para ambos é Guest.</span><span class="sxs-lookup"><span data-stu-id="219b8-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="219b8-132">Os usuários convidados são usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="219b8-132">Guest users are B2B users.</span></span>

<span data-ttu-id="219b8-133">O Microsoft Teams diferencia entre usuários convidados e usuários externos dentro do aplicativo, mas são usuários de B2B durante a autenticação.</span><span class="sxs-lookup"><span data-stu-id="219b8-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="219b8-134">Para obter mais informações sobre os usuários convidados e externos do Teams, consulte [habilitar o convidado e o acesso externo para o Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="219b8-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="219b8-135">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="219b8-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="219b8-136">Essa regra solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para a MFA em seu locatário inicial.</span><span class="sxs-lookup"><span data-stu-id="219b8-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="219b8-137">Ao acessar recursos em seu locatário, convidados e usuários externos precisam usar a MFA para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="219b8-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="219b8-138">Excluindo usuários convidados e externos da MFA baseada em riscos</span><span class="sxs-lookup"><span data-stu-id="219b8-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="219b8-139">Enquanto as organizações podem aplicar políticas com base em risco para usuários B2B usando a proteção de identidade, há limitações na implementação da proteção de identidade para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em sua casa Directory.</span><span class="sxs-lookup"><span data-stu-id="219b8-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="219b8-140">Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA.</span><span class="sxs-lookup"><span data-stu-id="219b8-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="219b8-141">Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="219b8-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="219b8-142">Excluindo usuários convidados e externos do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="219b8-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="219b8-143">Somente uma organização pode gerenciar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="219b8-143">Only one organization can manage a device.</span></span> <span data-ttu-id="219b8-144">Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários.</span><span class="sxs-lookup"><span data-stu-id="219b8-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="219b8-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="219b8-145">Next steps</span></span>

[<span data-ttu-id="219b8-146">Saiba como habilitar o acesso condicional do teams</span><span class="sxs-lookup"><span data-stu-id="219b8-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

