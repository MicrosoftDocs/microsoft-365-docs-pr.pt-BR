---
title: O que há de novo na pontuação segura da Microsoft
description: Descreve quais novas alterações ocorreram na pontuação segura da Microsoft na central de segurança do Microsoft 365.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373990"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="3e96b-104">O que há de novo na pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e96b-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3e96b-105">Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações.</span><span class="sxs-lookup"><span data-stu-id="3e96b-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="3e96b-106">Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="3e96b-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="3e96b-107">A pontuação segura da Microsoft pode ser encontrada em https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="3e96b-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="3e96b-108">Novembro de 2020</span><span class="sxs-lookup"><span data-stu-id="3e96b-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="3e96b-109">Foram adicionadas 3 ações de melhoria relacionadas aos serviços para o Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):</span><span class="sxs-lookup"><span data-stu-id="3e96b-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="3e96b-110">Corrigir o caminho de serviço sem cotação para os serviços do Windows</span><span class="sxs-lookup"><span data-stu-id="3e96b-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="3e96b-111">Alterar o caminho do executável do serviço para um local protegido comum</span><span class="sxs-lookup"><span data-stu-id="3e96b-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="3e96b-112">Alterar a conta de serviço para evitar a senha em cache no registro do Windows</span><span class="sxs-lookup"><span data-stu-id="3e96b-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="3e96b-113">Outubro de 2020</span><span class="sxs-lookup"><span data-stu-id="3e96b-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3e96b-114">Remover ação de melhoria relacionada ao Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="3e96b-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="3e96b-115">Definir a verificação de conteúdo da Web do aplicativo Windows Store SmartScreen do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="3e96b-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="3e96b-116">Agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="3e96b-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="3e96b-117">Ação de aprimoramento atualizada para o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3e96b-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="3e96b-118">Habilitar política para bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="3e96b-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="3e96b-119">Incompatibilidade com Pontuação segura de identidade e API de gráfico</span><span class="sxs-lookup"><span data-stu-id="3e96b-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="3e96b-120">Na versão recente da Pontuação segura da Microsoft, um modelo de Pontuação aprimorado foi lançado.</span><span class="sxs-lookup"><span data-stu-id="3e96b-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="3e96b-121">Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="3e96b-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="3e96b-122">No entanto, essas atualizações tornaram a pontuação segura da Microsoft temporariamente incompatível com a pontuação segura de identidade e a API do Graph.</span><span class="sxs-lookup"><span data-stu-id="3e96b-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="3e96b-123">No momento, a pontuação segura de identidade e a API do Graph adotarão o novo modelo de pontuação.</span><span class="sxs-lookup"><span data-stu-id="3e96b-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="3e96b-124">Até lá, os clientes verão as diferenças nas pontuações relatadas pela pontuação segura da Microsoft, Pontuação segura de identidade e API do Graph.</span><span class="sxs-lookup"><span data-stu-id="3e96b-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="3e96b-125">Lamentamos as inconveniências possíveis, e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.</span><span class="sxs-lookup"><span data-stu-id="3e96b-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="3e96b-126">Ações de aprimoramento atualizadas</span><span class="sxs-lookup"><span data-stu-id="3e96b-126">Updated improvement actions</span></span>

- <span data-ttu-id="3e96b-127">Foram adicionadas ações de melhoria do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3e96b-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="3e96b-128">Foram adicionadas ações de melhoria de identidade para o Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="3e96b-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="3e96b-129">Suporte para recomendações de segurança de [Gerenciamento de vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) do Microsoft defender for Endpoint &</span><span class="sxs-lookup"><span data-stu-id="3e96b-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="3e96b-130">Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora</span><span class="sxs-lookup"><span data-stu-id="3e96b-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="3e96b-131">Interface e funcionalidade atualizadas</span><span class="sxs-lookup"><span data-stu-id="3e96b-131">Updated interface and functionality</span></span>

* <span data-ttu-id="3e96b-132">Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO</span><span class="sxs-lookup"><span data-stu-id="3e96b-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="3e96b-133">Novas maneiras de acompanhar e avaliar a sua pontuação</span><span class="sxs-lookup"><span data-stu-id="3e96b-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="3e96b-134">Melhor controle e compreensão para regressões de Pontuação</span><span class="sxs-lookup"><span data-stu-id="3e96b-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="3e96b-135">Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento</span><span class="sxs-lookup"><span data-stu-id="3e96b-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="3e96b-136">Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas</span><span class="sxs-lookup"><span data-stu-id="3e96b-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="3e96b-137">E muito mais!</span><span class="sxs-lookup"><span data-stu-id="3e96b-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="3e96b-138">Queremos ouvir sua opinião</span><span class="sxs-lookup"><span data-stu-id="3e96b-138">We want to hear from you</span></span>

<span data-ttu-id="3e96b-139">Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="3e96b-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="3e96b-140">Estamos monitorando a Comunidade e forneceremos ajuda.</span><span class="sxs-lookup"><span data-stu-id="3e96b-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3e96b-141">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="3e96b-141">Related resources</span></span>

- [<span data-ttu-id="3e96b-142">Avaliar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="3e96b-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="3e96b-143">Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas</span><span class="sxs-lookup"><span data-stu-id="3e96b-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="3e96b-144">O que estar por vir.</span><span class="sxs-lookup"><span data-stu-id="3e96b-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
