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
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367102"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="96ec6-104">O que há de novo na pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="96ec6-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="96ec6-105">Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações.</span><span class="sxs-lookup"><span data-stu-id="96ec6-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="96ec6-106">Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="96ec6-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="96ec6-107">Novembro de 2020</span><span class="sxs-lookup"><span data-stu-id="96ec6-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="96ec6-108">Foram adicionadas 3 ações de melhoria relacionadas aos serviços para o Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):</span><span class="sxs-lookup"><span data-stu-id="96ec6-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="96ec6-109">Corrigir o caminho de serviço sem cotação para os serviços do Windows</span><span class="sxs-lookup"><span data-stu-id="96ec6-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="96ec6-110">Alterar o caminho do executável do serviço para um local protegido comum</span><span class="sxs-lookup"><span data-stu-id="96ec6-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="96ec6-111">Alterar a conta de serviço para evitar a senha em cache no registro do Windows</span><span class="sxs-lookup"><span data-stu-id="96ec6-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="96ec6-112">Outubro de 2020</span><span class="sxs-lookup"><span data-stu-id="96ec6-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="96ec6-113">Remover ação de melhoria relacionada ao Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="96ec6-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="96ec6-114">Definir a verificação de conteúdo da Web do aplicativo Windows Store SmartScreen do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="96ec6-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="96ec6-115">Agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="96ec6-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="96ec6-116">Ação de aprimoramento atualizada para o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="96ec6-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="96ec6-117">Habilitar política para bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="96ec6-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="96ec6-118">Incompatibilidade com Pontuação segura de identidade e API de gráfico</span><span class="sxs-lookup"><span data-stu-id="96ec6-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="96ec6-119">Na versão recente da Pontuação segura da Microsoft, um modelo de Pontuação aprimorado foi lançado.</span><span class="sxs-lookup"><span data-stu-id="96ec6-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="96ec6-120">Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="96ec6-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="96ec6-121">No entanto, essas atualizações tornaram a pontuação segura da Microsoft temporariamente incompatível com a pontuação segura de identidade e a API do Graph.</span><span class="sxs-lookup"><span data-stu-id="96ec6-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="96ec6-122">No momento, a pontuação segura de identidade e a API do Graph adotarão o novo modelo de pontuação.</span><span class="sxs-lookup"><span data-stu-id="96ec6-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="96ec6-123">Até lá, os clientes verão as diferenças nas pontuações relatadas pela pontuação segura da Microsoft, Pontuação segura de identidade e API do Graph.</span><span class="sxs-lookup"><span data-stu-id="96ec6-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="96ec6-124">Lamentamos as inconveniências possíveis, e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.</span><span class="sxs-lookup"><span data-stu-id="96ec6-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="96ec6-125">Ações de aprimoramento atualizadas</span><span class="sxs-lookup"><span data-stu-id="96ec6-125">Updated improvement actions</span></span>

- <span data-ttu-id="96ec6-126">Foram adicionadas ações de melhoria do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="96ec6-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="96ec6-127">Foram adicionadas ações de melhoria de identidade para o Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="96ec6-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="96ec6-128">Suporte para recomendações de segurança de [Gerenciamento de vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) do Microsoft defender for Endpoint &</span><span class="sxs-lookup"><span data-stu-id="96ec6-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="96ec6-129">Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora</span><span class="sxs-lookup"><span data-stu-id="96ec6-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="96ec6-130">Interface e funcionalidade atualizadas</span><span class="sxs-lookup"><span data-stu-id="96ec6-130">Updated interface and functionality</span></span>

* <span data-ttu-id="96ec6-131">Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO</span><span class="sxs-lookup"><span data-stu-id="96ec6-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="96ec6-132">Novas maneiras de acompanhar e avaliar a sua pontuação</span><span class="sxs-lookup"><span data-stu-id="96ec6-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="96ec6-133">Melhor controle e compreensão para regressões de Pontuação</span><span class="sxs-lookup"><span data-stu-id="96ec6-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="96ec6-134">Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento</span><span class="sxs-lookup"><span data-stu-id="96ec6-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="96ec6-135">Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas</span><span class="sxs-lookup"><span data-stu-id="96ec6-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="96ec6-136">E muito mais!</span><span class="sxs-lookup"><span data-stu-id="96ec6-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="96ec6-137">Queremos ouvir sua opinião</span><span class="sxs-lookup"><span data-stu-id="96ec6-137">We want to hear from you</span></span>

<span data-ttu-id="96ec6-138">Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="96ec6-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="96ec6-139">Estamos monitorando a Comunidade e forneceremos ajuda.</span><span class="sxs-lookup"><span data-stu-id="96ec6-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="96ec6-140">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="96ec6-140">Related resources</span></span>

- [<span data-ttu-id="96ec6-141">Avaliar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="96ec6-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="96ec6-142">Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas</span><span class="sxs-lookup"><span data-stu-id="96ec6-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="96ec6-143">O que estar por vir.</span><span class="sxs-lookup"><span data-stu-id="96ec6-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
