---
title: Verificar a saúde do serviço do Microsoft Defender para Ponto de Extremidade
description: Verifique a saúde do serviço do Microsoft Defender para o Ponto de Extremidade, veja se o serviço está enfrentando problemas e revise os problemas anteriores que foram resolvidos.
keywords: painel, serviço, problemas, saúde do serviço, status atual, histórico de status, resumo do impacto, causa raiz preliminar, resolução, tempo de resolução, tempo de resolução esperado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687620"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="e7162-104">Verificar a saúde do serviço do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e7162-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e7162-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e7162-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7162-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e7162-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="e7162-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e7162-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7162-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e7162-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="e7162-109">**A saúde** do serviço fornece informações sobre o status atual do serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e7162-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="e7162-110">Você poderá verificar se a saúde do serviço está saudável ou se há problemas atuais.</span><span class="sxs-lookup"><span data-stu-id="e7162-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="e7162-111">Se houver problemas, você verá informações como quando o problema foi detectado, qual é a causa raiz preliminar e o tempo de resolução esperado.</span><span class="sxs-lookup"><span data-stu-id="e7162-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="e7162-112">Você também verá informações sobre problemas históricos que foram resolvidos e detalhes como a data e a hora em que o problema foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="e7162-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="e7162-113">Quando não houver problemas no serviço, você verá um status saudável.</span><span class="sxs-lookup"><span data-stu-id="e7162-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="e7162-114">Você pode exibir detalhes sobre a saúde do  serviço clicando no painel operações de segurança ou selecionando o menu **de** saúde do serviço no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="e7162-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="e7162-115">A **página Detalhes de** saúde do serviço tem as seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="e7162-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="e7162-116">**Status atual**</span><span class="sxs-lookup"><span data-stu-id="e7162-116">**Current status**</span></span>
- <span data-ttu-id="e7162-117">**Histórico de status**</span><span class="sxs-lookup"><span data-stu-id="e7162-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="e7162-118">Status atual</span><span class="sxs-lookup"><span data-stu-id="e7162-118">Current status</span></span>
<span data-ttu-id="e7162-119">A **guia Status** atual mostra o estado atual do serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e7162-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="e7162-120">Quando o serviço está em execução suavemente, uma saúde de serviço saudável é mostrada.</span><span class="sxs-lookup"><span data-stu-id="e7162-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="e7162-121">Se houver problemas, os seguintes detalhes do serviço serão mostrados para ajudá-lo a obter informações sobre o problema:</span><span class="sxs-lookup"><span data-stu-id="e7162-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="e7162-122">Data e hora para quando o problema foi detectado</span><span class="sxs-lookup"><span data-stu-id="e7162-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="e7162-123">Uma breve descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e7162-123">A short description of the issue</span></span>
- <span data-ttu-id="e7162-124">Hora da atualização</span><span class="sxs-lookup"><span data-stu-id="e7162-124">Update time</span></span>
- <span data-ttu-id="e7162-125">Resumo do impacto</span><span class="sxs-lookup"><span data-stu-id="e7162-125">Summary of impact</span></span>
- <span data-ttu-id="e7162-126">Causa raiz preliminar</span><span class="sxs-lookup"><span data-stu-id="e7162-126">Preliminary root cause</span></span>
- <span data-ttu-id="e7162-127">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e7162-127">Next steps</span></span>
- <span data-ttu-id="e7162-128">Tempo de resolução esperado</span><span class="sxs-lookup"><span data-stu-id="e7162-128">Expected resolution time</span></span>

<span data-ttu-id="e7162-129">As atualizações sobre o andamento de um problema são refletidas na página à medida que o problema é resolvido.</span><span class="sxs-lookup"><span data-stu-id="e7162-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="e7162-130">Você verá atualizações sobre informações como um tempo de resolução de estimativa atualizado ou próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7162-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="e7162-131">Quando um problema é resolvido, ele é gravado na **guia Histórico de** status.</span><span class="sxs-lookup"><span data-stu-id="e7162-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="e7162-132">Histórico de status</span><span class="sxs-lookup"><span data-stu-id="e7162-132">Status history</span></span>
<span data-ttu-id="e7162-133">A **guia Histórico de** Status reflete todos os problemas históricos que foram vistos e resolvidos.</span><span class="sxs-lookup"><span data-stu-id="e7162-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="e7162-134">Você verá detalhes dos problemas resolvidos juntamente com as outras informações que foram incluídas enquanto estavam sendo resolvidas.</span><span class="sxs-lookup"><span data-stu-id="e7162-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="e7162-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7162-135">Related topic</span></span>
- [<span data-ttu-id="e7162-136">Exibir o painel de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="e7162-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
