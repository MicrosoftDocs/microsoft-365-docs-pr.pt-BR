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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683230"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="2e199-103">Políticas para permitir acesso B2B e de convidado externo</span><span class="sxs-lookup"><span data-stu-id="2e199-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="2e199-104">Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir o acesso a usuários convidados e externos que tenham uma conta de B2B (Business-to-Business) do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2e199-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="2e199-105">Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2e199-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="2e199-106">Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção.</span><span class="sxs-lookup"><span data-stu-id="2e199-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="2e199-107">No entanto, você também pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** .</span><span class="sxs-lookup"><span data-stu-id="2e199-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="2e199-108">Fornecer um caminho para contas B2B para autenticar com seu locatário do Azure AD não concede a essas contas acesso a todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="2e199-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="2e199-109">Os usuários B2B e suas contas têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos em políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2e199-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="2e199-110">Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados</span><span class="sxs-lookup"><span data-stu-id="2e199-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="2e199-111">Para proteger o acesso externo e de convidados com as contas B2B do Azure AD, o diagrama a seguir ilustra quais políticas serão adicionadas ou atualizadas das políticas comuns de acesso de dispositivo e identidade.</span><span class="sxs-lookup"><span data-stu-id="2e199-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="2e199-112">[![Resumo das atualizações de política para proteger o acesso de convidados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="2e199-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="2e199-113">Veja uma versão maior desta imagem</span><span class="sxs-lookup"><span data-stu-id="2e199-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="2e199-114">A tabela a seguir lista as políticas que você precisa criar e atualizar.</span><span class="sxs-lookup"><span data-stu-id="2e199-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="2e199-115">O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="2e199-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="2e199-116">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="2e199-116">Protection level</span></span>|<span data-ttu-id="2e199-117">Políticas</span><span class="sxs-lookup"><span data-stu-id="2e199-117">Policies</span></span>|<span data-ttu-id="2e199-118">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2e199-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="2e199-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="2e199-119">**Baseline**</span></span>|[<span data-ttu-id="2e199-120">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="2e199-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2e199-121">Crie essa nova política e configure:</span><span class="sxs-lookup"><span data-stu-id="2e199-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="2e199-122">Para as **atribuições > usuários e grupos > incluir**, escolha **Selecionar usuários e grupos** e, em seguida, selecione **todos os usuários convidados e externos**.</span><span class="sxs-lookup"><span data-stu-id="2e199-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="2e199-123">Para **atribuições > condições > entrar**, deixe todas as opções desmarcadas para sempre impor a autenticação multifator (MFA).</span><span class="sxs-lookup"><span data-stu-id="2e199-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="2e199-124">Exigir MFA quando o risco de entrada for *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="2e199-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2e199-125">Modifique esta política para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="2e199-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="2e199-126">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="2e199-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2e199-127">Modifique esta política para excluir usuários convidados e externos.</span><span class="sxs-lookup"><span data-stu-id="2e199-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="2e199-128">Para incluir ou excluir usuários convidados e externos em políticas de acesso condicional, para **atribuições > usuários e grupos > incluir** ou **excluir**, verifique **todos os usuários convidados e externos**.</span><span class="sxs-lookup"><span data-stu-id="2e199-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de tela de controles para exclusão de usuários convidados e externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="2e199-130">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2e199-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="2e199-131">Acesso externo e de convidados com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e199-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="2e199-132">O Microsoft Teams define o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2e199-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="2e199-133">O **acesso de convidados** usa uma conta de B2B do Azure AD que pode ser adicionada como um membro de uma equipe e ter todos os acessos com permissão para as comunicações e recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="2e199-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="2e199-134">O **acesso externo** é para um usuário externo que não tem uma conta B2B.</span><span class="sxs-lookup"><span data-stu-id="2e199-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="2e199-135">O acesso externo pode incluir convites e participação em chamadas, chats e reuniões, mas não inclui Associação de equipe e acesso aos recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="2e199-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="2e199-136">Para obter mais informações, consulte a [comparação entre o convidado e o acesso externo para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="2e199-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="2e199-137">Consulte [recomendações de política para proteger chats, grupos e arquivos de equipes](teams-access-policies.md) para obter mais informações sobre como proteger as políticas de acesso de dispositivo e identidade para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e199-137">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="2e199-138">Exigir a MFA sempre para usuários convidados e externos</span><span class="sxs-lookup"><span data-stu-id="2e199-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="2e199-139">Essa política solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para MFA em seu locatário de casa.</span><span class="sxs-lookup"><span data-stu-id="2e199-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="2e199-140">Ao acessar recursos em seu locatário, os usuários convidados e externos precisam usar a MFA para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="2e199-140">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="2e199-141">Excluindo usuários convidados e externos da MFA baseada em riscos</span><span class="sxs-lookup"><span data-stu-id="2e199-141">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="2e199-142">Enquanto as organizações podem reforçar políticas com base em risco para usuários B2B usando a proteção de identidade do Azure AD, há limitações na implementação da proteção de identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base.</span><span class="sxs-lookup"><span data-stu-id="2e199-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="2e199-143">Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA.</span><span class="sxs-lookup"><span data-stu-id="2e199-143">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="2e199-144">Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="2e199-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="2e199-145">Excluindo usuários convidados e externos do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2e199-145">Excluding guest and external users from device management</span></span>

<span data-ttu-id="2e199-146">Somente uma organização pode gerenciar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e199-146">Only one organization can manage a device.</span></span> <span data-ttu-id="2e199-147">Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários.</span><span class="sxs-lookup"><span data-stu-id="2e199-147">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="2e199-148">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2e199-148">Next step</span></span>

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2e199-150">Configure as políticas de acesso condicional para:</span><span class="sxs-lookup"><span data-stu-id="2e199-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2e199-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e199-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2e199-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2e199-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="2e199-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e199-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
