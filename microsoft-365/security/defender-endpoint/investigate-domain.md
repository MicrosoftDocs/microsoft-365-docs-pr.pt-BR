---
title: Investigar o Microsoft Defender para domínios de ponto de extremidade
description: Use as opções de investigação para ver se dispositivos e servidores estão se comunicando com domínios mal-intencionados.
keywords: investigar domínio, domínio, domínio mal-intencionado, microsoft defender atp, alerta, URL
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b2e858a7533c17bc5c425ec1de73a45eaf5b6b31
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053779"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="be653-104">Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="be653-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="be653-105">**Applies to:**</span></span>
- [<span data-ttu-id="be653-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="be653-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be653-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="be653-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="be653-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="be653-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="be653-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="be653-110">Investigue um domínio para ver se dispositivos e servidores em sua rede corporativa estão se comunicando com um domínio mal-intencionado conhecido.</span><span class="sxs-lookup"><span data-stu-id="be653-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="be653-111">Você pode investigar um domínio usando o recurso de pesquisa ou clicando em um link de domínio da linha do tempo **do dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="be653-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="be653-112">Você pode ver informações das seções a seguir no exibição url:</span><span class="sxs-lookup"><span data-stu-id="be653-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="be653-113">Detalhes da URL, Contatos, Nameservers</span><span class="sxs-lookup"><span data-stu-id="be653-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="be653-114">Alertas relacionados a essa URL</span><span class="sxs-lookup"><span data-stu-id="be653-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="be653-115">URL na organização</span><span class="sxs-lookup"><span data-stu-id="be653-115">URL in organization</span></span>
- <span data-ttu-id="be653-116">Dispositivos observados mais recentes com URL</span><span class="sxs-lookup"><span data-stu-id="be653-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="be653-117">URL em todo o mundo</span><span class="sxs-lookup"><span data-stu-id="be653-117">URL worldwide</span></span>

<span data-ttu-id="be653-118">A **seção URL Worldwide** lista a URL, um link para mais detalhes em Whois, o número de incidentes abertos relacionados e o número de alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="be653-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="be653-119">Incidente</span><span class="sxs-lookup"><span data-stu-id="be653-119">Incident</span></span>

<span data-ttu-id="be653-120">O **cartão** Incident exibe um gráfico de barras de todos os alertas ativos em incidentes nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="be653-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="be653-121">Prevalência</span><span class="sxs-lookup"><span data-stu-id="be653-121">Prevalence</span></span>

<span data-ttu-id="be653-122">O **Cartão de** Prevalência fornece detalhes sobre a prevalência da URL dentro da organização, por um período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="be653-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="be653-123">Embora o período de tempo padrão seja os últimos 30 dias, você pode personalizar o intervalo selecionando a seta apontando para baixo no canto do cartão.</span><span class="sxs-lookup"><span data-stu-id="be653-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="be653-124">O intervalo mais curto disponível é para prevalência no último dia, enquanto o intervalo mais longo é nos últimos 6 meses.</span><span class="sxs-lookup"><span data-stu-id="be653-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="be653-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="be653-125">Alerts</span></span>

<span data-ttu-id="be653-126">A **guia Alertas** fornece uma lista de alertas associados à URL.</span><span class="sxs-lookup"><span data-stu-id="be653-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="be653-127">A tabela mostrada aqui é uma versão filtrada dos alertas visíveis na tela de fila de alertas, mostrando apenas alertas associados ao domínio, sua gravidade, status, o incidente associado, classificação, estado de investigação e muito mais.</span><span class="sxs-lookup"><span data-stu-id="be653-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="be653-128">A guia Alertas pode ser ajustada para mostrar mais ou menos informações, selecionando **Personalizar colunas** no menu ação acima dos headers da coluna.</span><span class="sxs-lookup"><span data-stu-id="be653-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="be653-129">O número de itens exibidos também pode ser ajustado selecionando **itens por página** no mesmo menu.</span><span class="sxs-lookup"><span data-stu-id="be653-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="be653-130">Observado na organização</span><span class="sxs-lookup"><span data-stu-id="be653-130">Observed in organization</span></span>

<span data-ttu-id="be653-131">A **guia Observado na organização** fornece uma exibição cronológica sobre os eventos e alertas associados que foram observados na URL.</span><span class="sxs-lookup"><span data-stu-id="be653-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="be653-132">Essa guia inclui uma linha do tempo e um evento de listagem de tabela personalizável, como a hora, o dispositivo e uma breve descrição do que aconteceu.</span><span class="sxs-lookup"><span data-stu-id="be653-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="be653-133">Você pode exibir eventos de diferentes períodos de tempo inserindo as datas nos campos de texto acima dos headers da tabela.</span><span class="sxs-lookup"><span data-stu-id="be653-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="be653-134">Você também pode personalizar o intervalo de tempo selecionando diferentes áreas da linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="be653-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="be653-135">**Investigar um domínio:**</span><span class="sxs-lookup"><span data-stu-id="be653-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="be653-136">Selecione **URL** no menu suspenso **barra de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="be653-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="be653-137">Insira a URL no **campo** Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="be653-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="be653-138">Clique no ícone de pesquisa ou pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="be653-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="be653-139">Os detalhes sobre a URL são exibidos.</span><span class="sxs-lookup"><span data-stu-id="be653-139">Details about the URL are displayed.</span></span> <span data-ttu-id="be653-140">Observação: os resultados da pesquisa só serão retornados para URLs observadas nas comunicações de dispositivos na organização.</span><span class="sxs-lookup"><span data-stu-id="be653-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="be653-141">Use os filtros de pesquisa para definir os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="be653-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="be653-142">Você também pode usar a caixa de pesquisa linha do tempo para filtrar os resultados exibidos de todos os dispositivos na organização observados se comunicando com a URL, o arquivo associado à comunicação e a última data observada.</span><span class="sxs-lookup"><span data-stu-id="be653-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="be653-143">Clicar em qualquer um dos nomes de dispositivo o levará ao ponto de vista desse dispositivo, onde você pode continuar a investigar alertas, comportamentos e eventos relatados.</span><span class="sxs-lookup"><span data-stu-id="be653-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="be653-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="be653-144">Related topics</span></span>
- [<span data-ttu-id="be653-145">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="be653-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="be653-146">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="be653-147">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="be653-148">Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="be653-149">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="be653-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="be653-150">Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="be653-151">Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="be653-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
