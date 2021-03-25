---
title: Técnicas na linha do tempo do dispositivo
description: Noções básicas sobre a linha do tempo do dispositivo no Microsoft Defender para Ponto de Extremidade
keywords: linha do tempo do dispositivo, ponto de extremidade, MITRE, MITRE ATT&CK, técnicas, táticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185462"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="72538-104">Técnicas na linha do tempo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="72538-104">Techniques in the device timeline</span></span>


<span data-ttu-id="72538-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="72538-105">**Applies to:**</span></span>
- [<span data-ttu-id="72538-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="72538-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="72538-107">Você pode obter mais informações em uma investigação analisando os eventos que aconteceram em um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="72538-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="72538-108">Primeiro, selecione o dispositivo de interesse na lista [Dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="72538-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="72538-109">Na página do dispositivo, você pode selecionar a guia **Linha** do Tempo para exibir todos os eventos que ocorreram no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72538-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="72538-110">Compreender técnicas na linha do tempo</span><span class="sxs-lookup"><span data-stu-id="72538-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="72538-111">Algumas informações se relacionam a um recurso de produto pré-lançado na visualização pública que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="72538-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="72538-112">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="72538-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="72538-113">No Microsoft Defender para Ponto de Extremidade, **as** técnicas são um tipo de dados adicional na linha do tempo do evento.</span><span class="sxs-lookup"><span data-stu-id="72538-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="72538-114">As técnicas fornecem mais informações sobre as atividades associadas ao [MITRE ATT&](https://attack.mitre.org/) técnicas de CK ou sub-técnicas.</span><span class="sxs-lookup"><span data-stu-id="72538-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="72538-115">Esse recurso simplifica a experiência de investigação ajudando os analistas a entender as atividades observadas em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72538-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="72538-116">Os analistas podem, então, decidir investigar mais.</span><span class="sxs-lookup"><span data-stu-id="72538-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="72538-117">Para visualização pública, as técnicas estão disponíveis por padrão e mostradas em conjunto com eventos quando a linha do tempo de um dispositivo é exibida.</span><span class="sxs-lookup"><span data-stu-id="72538-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Técnicas na captura de tela da linha do tempo do dispositivo](images/device-timeline-2.png)

<span data-ttu-id="72538-119">As técnicas são realçadas em negrito e aparecem com um ícone azul à esquerda.</span><span class="sxs-lookup"><span data-stu-id="72538-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="72538-120">O nome e a técnica correspondentes do MITRE ATT&ID de CK também aparecem como marcas em Informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="72538-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="72538-121">Opções de pesquisa e exportação também estão disponíveis para Técnicas.</span><span class="sxs-lookup"><span data-stu-id="72538-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="72538-122">Investigar usando o painel lateral</span><span class="sxs-lookup"><span data-stu-id="72538-122">Investigate using the side pane</span></span>

<span data-ttu-id="72538-123">Selecione uma Técnica para abrir seu painel lateral correspondente.</span><span class="sxs-lookup"><span data-stu-id="72538-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="72538-124">Aqui você pode ver informações adicionais e insights como att&técnicas de CK relacionadas, táticas e descrições.</span><span class="sxs-lookup"><span data-stu-id="72538-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="72538-125">Selecione a técnica *de Ataque específica* para abrir a página de técnica de CK&ATT relacionada, onde você pode encontrar mais informações sobre ele.</span><span class="sxs-lookup"><span data-stu-id="72538-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="72538-126">Você pode copiar os detalhes de uma entidade quando vir um ícone azul à direita.</span><span class="sxs-lookup"><span data-stu-id="72538-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="72538-127">Por exemplo, para copiar SHA1 de um arquivo relacionado, selecione o ícone de página azul.</span><span class="sxs-lookup"><span data-stu-id="72538-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Copiar detalhes da entidade](images/techniques-side-pane-clickable.png)

<span data-ttu-id="72538-129">Você pode fazer o mesmo para linhas de comando.</span><span class="sxs-lookup"><span data-stu-id="72538-129">You can do the same for command lines.</span></span>

![Copiar linha de comando](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="72538-131">Investigar eventos relacionados</span><span class="sxs-lookup"><span data-stu-id="72538-131">Investigate related events</span></span>

<span data-ttu-id="72538-132">Para usar [a busca avançada](advanced-hunting-overview.md) para encontrar eventos relacionados à Técnica selecionada, selecione Procurar eventos **relacionados.**</span><span class="sxs-lookup"><span data-stu-id="72538-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="72538-133">Isso leva à página de busca avançada com uma consulta para encontrar eventos relacionados à Técnica.</span><span class="sxs-lookup"><span data-stu-id="72538-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Busca por eventos relacionados](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="72538-135">A consulta usando o botão **Procurar** eventos relacionados a partir de um painel lateral de Técnica exibe todos os eventos relacionados à técnica identificada, mas não inclui a técnica em si nos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="72538-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="72538-136">Personalizar a linha do tempo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="72538-136">Customize your device timeline</span></span>

<span data-ttu-id="72538-137">No lado superior direito da linha do tempo do dispositivo, você pode escolher um intervalo de datas para limitar o número de eventos e técnicas na linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="72538-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="72538-138">Você pode personalizar quais colunas expor.</span><span class="sxs-lookup"><span data-stu-id="72538-138">You can customize which columns to expose.</span></span> <span data-ttu-id="72538-139">Você também pode filtrar eventos sinalizados por tipo de dados ou por grupo de eventos.</span><span class="sxs-lookup"><span data-stu-id="72538-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="72538-140">Escolher colunas para expor</span><span class="sxs-lookup"><span data-stu-id="72538-140">Choose columns to expose</span></span>
<span data-ttu-id="72538-141">Você pode escolher quais colunas expor na linha do tempo selecionando o **botão Escolher colunas.**</span><span class="sxs-lookup"><span data-stu-id="72538-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Personalizar colunas](images/filter-customize-columns.png)

<span data-ttu-id="72538-143">A partir daí, você pode selecionar quais informações serão definidas para incluir.</span><span class="sxs-lookup"><span data-stu-id="72538-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="72538-144">Filtrar para exibir apenas técnicas ou eventos</span><span class="sxs-lookup"><span data-stu-id="72538-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="72538-145">Para exibir apenas eventos ou técnicas, selecione **Filtros** na linha do tempo do dispositivo e escolha seu tipo de dados preferencial para exibir.</span><span class="sxs-lookup"><span data-stu-id="72538-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Filtra captura de tela](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="72538-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="72538-147">See also</span></span>
- [<span data-ttu-id="72538-148">Exibir e organizar a lista Dispositivos</span><span class="sxs-lookup"><span data-stu-id="72538-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="72538-149">Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72538-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
