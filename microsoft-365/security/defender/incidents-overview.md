---
title: Incidentes no Microsoft 365 Defender
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861618"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="1c7d8-104">Incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c7d8-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1c7d8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1c7d8-105">**Applies to:**</span></span>
- <span data-ttu-id="1c7d8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c7d8-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="1c7d8-107">Quer experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="1c7d8-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1c7d8-108">Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="1c7d8-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="1c7d8-109">Um incidente no Microsoft 365 Defender é uma coleção de alertas correlacionados e dados associados que comentam a história de um ataque.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="1c7d8-110">Os serviços e aplicativos do Microsoft 365 criam alertas quando detectam um evento ou atividade suspeito ou mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="1c7d8-111">Alertas individuais fornecem dicas valiosas sobre um ataque concluído ou contínuo.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="1c7d8-112">No entanto, os ataques geralmente empregam várias técnicas contra diferentes tipos de entidades, como dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="1c7d8-113">O resultado são vários alertas para várias entidades em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="1c7d8-114">Como reunir os alertas individuais para obter informações sobre um ataque pode ser desafiador e demorado, o Microsoft 365 Defender agrega automaticamente os alertas e suas informações associadas a um incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Como o Microsoft 365 Defender correlaciona eventos de entidades em um incidente":::

<span data-ttu-id="1c7d8-116">Assista a esta breve visão geral dos incidentes no Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="1c7d8-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="1c7d8-117">Agrupar alertas relacionados a um incidente oferece uma visão abrangente de um ataque.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="1c7d8-118">Por exemplo, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="1c7d8-118">For example, you can see:</span></span>

- <span data-ttu-id="1c7d8-119">Onde o ataque começou.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-119">Where the attack started.</span></span>
- <span data-ttu-id="1c7d8-120">Quais táticas foram usadas.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-120">What tactics were used.</span></span>
- <span data-ttu-id="1c7d8-121">Até que ponto o ataque foi para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="1c7d8-122">O escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="1c7d8-123">Todos os dados associados ao ataque.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="1c7d8-124">Se [habilitado, o](m365d-enable.md)Microsoft 365 Defender pode investigar e resolver alertas automaticamente por meio da automação e da inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="1c7d8-125">Você também pode executar etapas de correção adicionais para resolver o ataque.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="1c7d8-126">Incidentes e alertas no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c7d8-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="1c7d8-127">Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="1c7d8-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="1c7d8-128">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="A página Incidentes no centro de segurança do Microsoft 365":::

<span data-ttu-id="1c7d8-130">Selecionar um nome de incidente exibe um resumo do incidente e fornece acesso a guias com informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro de segurança do Microsoft 365":::

<span data-ttu-id="1c7d8-132">As guias adicionais para um incidente são:</span><span class="sxs-lookup"><span data-stu-id="1c7d8-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="1c7d8-133">Alertas</span><span class="sxs-lookup"><span data-stu-id="1c7d8-133">Alerts</span></span> 

  <span data-ttu-id="1c7d8-134">Todos os alertas relacionados ao incidente e suas informações.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="1c7d8-135">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="1c7d8-135">Devices</span></span>

  <span data-ttu-id="1c7d8-136">Todos os dispositivos que foram identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="1c7d8-137">Usuários</span><span class="sxs-lookup"><span data-stu-id="1c7d8-137">Users</span></span>

  <span data-ttu-id="1c7d8-138">Todos os usuários identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="1c7d8-139">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="1c7d8-139">Mailboxes</span></span>

  <span data-ttu-id="1c7d8-140">Todas as caixas de correio identificadas para fazer parte ou relacionadas ao incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="1c7d8-141">Investigações</span><span class="sxs-lookup"><span data-stu-id="1c7d8-141">Investigations</span></span>

  <span data-ttu-id="1c7d8-142">Todas as investigações automatizadas disparadas por alertas no incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="1c7d8-143">Evidências e resposta</span><span class="sxs-lookup"><span data-stu-id="1c7d8-143">Evidence and Response</span></span>

  <span data-ttu-id="1c7d8-144">Todos os eventos com suporte e entidades suspeitas nos alertas no incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="1c7d8-145">Aqui está a relação entre um incidente e seus dados e as guias de um incidente no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="A relação de um incidente e seus dados com as guias de um incidente no centro de segurança do Microsoft 365":::

## <a name="next-step"></a><span data-ttu-id="1c7d8-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1c7d8-147">Next step</span></span>

<span data-ttu-id="1c7d8-148">A fila de **incidentes da página Incidentes** lista os incidentes mais recentes.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="1c7d8-149">A partir daqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="1c7d8-149">From here, you can:</span></span>

- <span data-ttu-id="1c7d8-150">Confira quais incidentes devem ser [priorizados](incident-queue.md) com base na gravidade e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="1c7d8-151">Execute uma [investigação](investigate-incidents.md) de um incidente.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="1c7d8-152">[Gerencie incidentes](manage-incidents.md), que inclui renomeação, atribuição, classificação e adição de marcas para o fluxo de trabalho de gerenciamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="1c7d8-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
