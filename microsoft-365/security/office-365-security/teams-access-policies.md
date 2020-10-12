---
title: Políticas de equipe recomendadas-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve as políticas para as recomendações da Microsoft sobre como proteger a comunicação de equipes e o acesso a arquivos.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 6949e72b9f70464221b9aff7137b8ec034a3b04f
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399618"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="15b2a-103">Recomendações de política para proteger chats, grupos e arquivos de equipes</span><span class="sxs-lookup"><span data-stu-id="15b2a-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="15b2a-104">Este artigo descreve como implementar as políticas de acesso de dispositivo e identidade recomendadas para proteger chat, grupos e conteúdo do Microsoft Teams, como arquivos e calendários.</span><span class="sxs-lookup"><span data-stu-id="15b2a-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="15b2a-105">Este guia baseia-se nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md), com informações adicionais específicas para equipes.</span><span class="sxs-lookup"><span data-stu-id="15b2a-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="15b2a-106">Como as equipes se integram com nossos outros produtos, também Confira [recomendações de política para proteger sites e arquivos do SharePoint](sharepoint-file-access-policies.md) e [recomendações de política para proteger o email](secure-email-recommended-policies.md).</span><span class="sxs-lookup"><span data-stu-id="15b2a-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="15b2a-107">Essas recomendações são baseadas em três camadas diferentes de segurança e proteção para equipes que podem ser aplicadas com base na granularidade das suas necessidades: linha de base, confidencial e altamente regulamentada.</span><span class="sxs-lookup"><span data-stu-id="15b2a-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="15b2a-108">Você pode saber mais sobre essas camadas de segurança e as políticas recomendadas referenciadas por essas recomendações nas [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="15b2a-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="15b2a-109">Recomendações adicionais específicas para a implantação do teams estão incluídas neste artigo para abranger circunstâncias de autenticação específicas, incluindo para usuários fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="15b2a-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="15b2a-110">Será necessário seguir estas orientações para uma experiência de segurança completa.</span><span class="sxs-lookup"><span data-stu-id="15b2a-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="15b2a-111">Introdução ao Teams antes de outros serviços dependentes</span><span class="sxs-lookup"><span data-stu-id="15b2a-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="15b2a-112">Você não precisa habilitar os serviços dependentes para começar a usar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15b2a-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="15b2a-113">Isso tudo funcionará.</span><span class="sxs-lookup"><span data-stu-id="15b2a-113">These will all "just work."</span></span> <span data-ttu-id="15b2a-114">No entanto, você precisa estar preparado para gerenciar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15b2a-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="15b2a-115">Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15b2a-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="15b2a-116">Sites de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="15b2a-116">SharePoint team sites</span></span>
- <span data-ttu-id="15b2a-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="15b2a-117">OneDrive for Business</span></span>
- <span data-ttu-id="15b2a-118">Caixas de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="15b2a-118">Exchange mailboxes</span></span>
- <span data-ttu-id="15b2a-119">Transmitir vídeos e planos do Planner (se esses serviços estiverem habilitados)</span><span class="sxs-lookup"><span data-stu-id="15b2a-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="15b2a-120">Atualizando políticas comuns para incluir o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="15b2a-121">Para proteger o chat, os grupos e o conteúdo no Microsoft Teams, o diagrama a seguir ilustra quais políticas serão atualizadas a partir das políticas comuns de acesso de dispositivo e identidade.</span><span class="sxs-lookup"><span data-stu-id="15b2a-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="15b2a-122">Para cada política a ser atualizada, verifique se o Microsoft Teams e os serviços dependentes estão incluídos na atribuição de aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="15b2a-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="15b2a-123">[![Resumo das atualizações de política para proteger o acesso ao Microsoft Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="15b2a-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

[<span data-ttu-id="15b2a-124">Veja uma versão maior desta imagem</span><span class="sxs-lookup"><span data-stu-id="15b2a-124">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

<span data-ttu-id="15b2a-125">Estes são os serviços dependentes a serem incluídos na atribuição de aplicativos de nuvem para o Teams:</span><span class="sxs-lookup"><span data-stu-id="15b2a-125">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="15b2a-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-126">Microsoft Teams</span></span>
- <span data-ttu-id="15b2a-127">SharePoint e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="15b2a-127">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="15b2a-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="15b2a-128">Exchange Online</span></span>
- <span data-ttu-id="15b2a-129">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15b2a-129">Skype for Business Online</span></span>
- <span data-ttu-id="15b2a-130">Microsoft Stream (gravações de reunião)</span><span class="sxs-lookup"><span data-stu-id="15b2a-130">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="15b2a-131">Microsoft Planner (tarefas do Planner e planejar dados)</span><span class="sxs-lookup"><span data-stu-id="15b2a-131">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="15b2a-132">Esta tabela lista as políticas que precisam ser revisitadas e links para cada política nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md), que tem a política mais ampla definida para todos os aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="15b2a-132">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="15b2a-133">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="15b2a-133">Protection level</span></span>|<span data-ttu-id="15b2a-134">Políticas</span><span class="sxs-lookup"><span data-stu-id="15b2a-134">Policies</span></span>|<span data-ttu-id="15b2a-135">Informações adicionais para implementação do teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-135">Further information for Teams implementation</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="15b2a-136">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="15b2a-136">**Baseline**</span></span>|[<span data-ttu-id="15b2a-137">Exigir MFA quando o risco de entrada for *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="15b2a-137">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="15b2a-138">Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="15b2a-138">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="15b2a-139">O Microsoft Teams tem acesso de convidado e regras de acesso externo para considerar também, você aprenderá mais sobre eles posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="15b2a-139">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
|        |[<span data-ttu-id="15b2a-140">Bloquear clientes sem suporte para a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="15b2a-140">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="15b2a-141">Inclua equipes e serviços dependentes na atribuição de aplicativos em nuvem.</span><span class="sxs-lookup"><span data-stu-id="15b2a-141">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="15b2a-142">Usuários de alto risco devem alterar a senha</span><span class="sxs-lookup"><span data-stu-id="15b2a-142">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="15b2a-143">Obriga os usuários do teams a alterarem suas senhas ao entrarem se uma atividade de alto risco for detectada para sua conta.</span><span class="sxs-lookup"><span data-stu-id="15b2a-143">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="15b2a-144">Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="15b2a-144">Be sure Teams and dependent services are included in the list of apps.</span></span>|
|        |[<span data-ttu-id="15b2a-145">Aplicar políticas de proteção de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="15b2a-145">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="15b2a-146">Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="15b2a-146">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="15b2a-147">Atualize a política para cada plataforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="15b2a-147">Update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="15b2a-148">Definir políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15b2a-148">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="15b2a-149">Inclua equipes e serviços dependentes nessa política.</span><span class="sxs-lookup"><span data-stu-id="15b2a-149">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="15b2a-150">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="15b2a-150">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="15b2a-151">Inclua equipes e serviços dependentes nessa política.</span><span class="sxs-lookup"><span data-stu-id="15b2a-151">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="15b2a-152">**Confidencial**</span><span class="sxs-lookup"><span data-stu-id="15b2a-152">**Sensitive**</span></span>|[<span data-ttu-id="15b2a-153">Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*</span><span class="sxs-lookup"><span data-stu-id="15b2a-153">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="15b2a-154">O Microsoft Teams tem acesso de convidado e regras de acesso externo para considerar também, você aprenderá mais sobre eles posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="15b2a-154">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="15b2a-155">Inclua equipes e serviços dependentes nessa política.</span><span class="sxs-lookup"><span data-stu-id="15b2a-155">Include Teams and dependent services in this policy.</span></span>|
|         |[<span data-ttu-id="15b2a-156">Exigir computadores *em conformidade e* dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="15b2a-156">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="15b2a-157">Inclua equipes e serviços dependentes nessa política.</span><span class="sxs-lookup"><span data-stu-id="15b2a-157">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="15b2a-158">**Altamente controlado**</span><span class="sxs-lookup"><span data-stu-id="15b2a-158">**Highly regulated**</span></span>|[<span data-ttu-id="15b2a-159">*Sempre* exigir MFA</span><span class="sxs-lookup"><span data-stu-id="15b2a-159">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="15b2a-160">Independentemente da identidade do usuário, a MFA será usada pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="15b2a-160">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="15b2a-161">Inclua equipes e serviços dependentes nessa política.</span><span class="sxs-lookup"><span data-stu-id="15b2a-161">Include Teams and dependent services in this policy.</span></span> |
| | |

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="15b2a-162">Arquitetura de serviços dependentes do teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-162">Teams dependent services architecture</span></span>

<span data-ttu-id="15b2a-163">Para referência, o diagrama a seguir ilustra a equipe de serviços que se baseia no.</span><span class="sxs-lookup"><span data-stu-id="15b2a-163">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="15b2a-164">Para obter mais informações e ilustrações adicionais, consulte [Microsoft Teams e serviços de produtividade relacionados no microsoft 365 para arquitetos de ti](../../solutions/productivity-illustrations.md).</span><span class="sxs-lookup"><span data-stu-id="15b2a-164">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="15b2a-165">[![Diagrama mostrando dependências do teams no SharePoint, no OneDrive for Business e no Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="15b2a-165">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="15b2a-166">Veja uma versão maior desta imagem</span><span class="sxs-lookup"><span data-stu-id="15b2a-166">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="15b2a-167">Acesso externo e de convidados para o Teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-167">Guest and external access for Teams</span></span>

<span data-ttu-id="15b2a-168">O Microsoft Teams define o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15b2a-168">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="15b2a-169">O **acesso de convidados** usa uma conta B2B do Azure ad para um usuário convidado ou externo que pode ser adicionado como um membro de uma equipe e ter todos os acessos com permissão para a comunicação e recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="15b2a-169">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="15b2a-170">O **acesso externo** é para um usuário externo que não tem uma conta B2B do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="15b2a-170">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="15b2a-171">O acesso externo pode incluir convites e participação em chamadas, chats e reuniões, mas não inclui Associação de equipe e acesso aos recursos da equipe.</span><span class="sxs-lookup"><span data-stu-id="15b2a-171">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="15b2a-172">As políticas de acesso condicional só se aplicam ao acesso de convidados no Teams porque há uma conta B2B do Azure AD correspondente.</span><span class="sxs-lookup"><span data-stu-id="15b2a-172">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

<span data-ttu-id="15b2a-173">Para as políticas recomendadas para permitir o acesso a usuários convidados e externos com uma conta B2B do Azure AD, consulte [políticas para permitir acesso a contas de convidados e externos](identity-access-policies-guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="15b2a-173">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="15b2a-174">Acesso de convidado ao Teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-174">Guest access in Teams</span></span>

<span data-ttu-id="15b2a-175">Além das políticas para usuários internos à sua empresa ou organização, os administradores podem habilitar o acesso de convidados para permitir, em uma base de usuário por usuário, as pessoas que são externas à sua empresa ou organização para acessar os recursos do Teams e interagir com pessoas internas para tarefas como conversas de grupo, chat e reuniões.</span><span class="sxs-lookup"><span data-stu-id="15b2a-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span> 

<span data-ttu-id="15b2a-176">Para obter mais informações sobre o acesso de convidados e como implementá-lo, consulte  [Teams Guest Access](https://docs.microsoft.com/microsoftteams/guest-access).</span><span class="sxs-lookup"><span data-stu-id="15b2a-176">For more information about guest access and how to implement it, see  [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="15b2a-177">Acesso externo no Teams</span><span class="sxs-lookup"><span data-stu-id="15b2a-177">External access in Teams</span></span>

<span data-ttu-id="15b2a-178">O acesso externo às vezes é confundido com acesso de convidados, portanto, é importante ficar claro que esses dois mecanismos de acesso não internos são realmente muito diferentes.</span><span class="sxs-lookup"><span data-stu-id="15b2a-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span> 

<span data-ttu-id="15b2a-179">O acesso externo é uma maneira para os usuários do teams de um domínio externo inteiro localizar, chamar, bater papo e configurar reuniões com seus usuários no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15b2a-179">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="15b2a-180">Os administradores do teams configuram o acesso externo no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="15b2a-180">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="15b2a-181">Para obter mais informações, consulte [gerenciar o acesso externo no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="15b2a-181">For more information, see [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="15b2a-182">Usuários de acesso externo têm menos acesso e funcionalidade do que um indivíduo que foi adicionado por meio de acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="15b2a-182">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="15b2a-183">Por exemplo, usuários de acesso externo podem bater papo com seus usuários internos com o Teams, mas não podem acessar canais de equipe, arquivos ou outros recursos.</span><span class="sxs-lookup"><span data-stu-id="15b2a-183">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="15b2a-184">O acesso externo não usa contas de usuário B2B do Azure AD e, portanto, não usa políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="15b2a-184">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span> 

## <a name="teams-policies"></a><span data-ttu-id="15b2a-185">Políticas de equipes</span><span class="sxs-lookup"><span data-stu-id="15b2a-185">Teams policies</span></span>

<span data-ttu-id="15b2a-186">Fora das políticas comuns listadas acima, há políticas específicas de equipes que podem e devem ser configuradas para gerenciar várias funcionalidades de equipes.</span><span class="sxs-lookup"><span data-stu-id="15b2a-186">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="15b2a-187">Políticas de equipes e canais</span><span class="sxs-lookup"><span data-stu-id="15b2a-187">Teams and channels policies</span></span>

<span data-ttu-id="15b2a-188">Equipes e canais são dois elementos comumente usados no Microsoft Teams, e há políticas que podem ser colocadas em vigor para controlar o que os usuários podem ou não fazer ao usar equipes e canais.</span><span class="sxs-lookup"><span data-stu-id="15b2a-188">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="15b2a-189">Embora você possa criar uma equipe global, se sua organização tiver 5000 usuários ou menos, é provável que você ache útil ter equipes e canais menores para fins específicos, em linha com suas necessidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="15b2a-189">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="15b2a-190">É recomendável alterar a política padrão ou criar políticas personalizadas, e você pode saber mais sobre o gerenciamento de suas políticas neste link: [gerenciar políticas de equipes no Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span><span class="sxs-lookup"><span data-stu-id="15b2a-190">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="15b2a-191">Políticas de mensagens</span><span class="sxs-lookup"><span data-stu-id="15b2a-191">Messaging policies</span></span>

<span data-ttu-id="15b2a-192">Mensagens, ou chat, também podem ser gerenciadas por meio da política global padrão, ou por meio de políticas personalizadas, e isso pode ajudar os usuários a se comunicar uns com os outros de forma adequada à sua organização.</span><span class="sxs-lookup"><span data-stu-id="15b2a-192">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="15b2a-193">Essas informações podem ser revisadas no [Gerenciamento de políticas de mensagens no Microsoft Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span><span class="sxs-lookup"><span data-stu-id="15b2a-193">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="15b2a-194">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="15b2a-194">Meeting policies</span></span>

<span data-ttu-id="15b2a-195">Nenhuma discussão sobre o Teams seria concluída sem planejamento e implementação de políticas em relação às reuniões do teams.</span><span class="sxs-lookup"><span data-stu-id="15b2a-195">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="15b2a-196">As reuniões são um componente essencial do Teams, permitindo que as pessoas atendam formalmente e apresentem vários usuários de uma só vez, além de compartilhar conteúdo relevante para a reunião.</span><span class="sxs-lookup"><span data-stu-id="15b2a-196">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="15b2a-197">A definição das políticas corretas para sua organização em relação às reuniões é essencial.</span><span class="sxs-lookup"><span data-stu-id="15b2a-197">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="15b2a-198">Consulte [gerenciar políticas de reunião no Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="15b2a-198">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="15b2a-199">Políticas de permissão de aplicativo</span><span class="sxs-lookup"><span data-stu-id="15b2a-199">App permission policies</span></span>

<span data-ttu-id="15b2a-200">O Microsoft Teams também permite que você use aplicativos em vários lugares, como canais ou chats pessoais.</span><span class="sxs-lookup"><span data-stu-id="15b2a-200">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="15b2a-201">Ter políticas em torno de quais aplicativos podem ser adicionados e usados e, em que, é essencial manter um ambiente rico em conteúdo que também é seguro.</span><span class="sxs-lookup"><span data-stu-id="15b2a-201">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="15b2a-202">Para obter mais informações sobre políticas de permissão de aplicativo, confira [Manage app Permission Policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="15b2a-202">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="15b2a-203">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="15b2a-203">Next steps</span></span>

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="15b2a-205">Configure as políticas de acesso condicional para:</span><span class="sxs-lookup"><span data-stu-id="15b2a-205">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="15b2a-206">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="15b2a-206">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="15b2a-207">SharePoint</span><span class="sxs-lookup"><span data-stu-id="15b2a-207">SharePoint</span></span>](sharepoint-file-access-policies.md)
