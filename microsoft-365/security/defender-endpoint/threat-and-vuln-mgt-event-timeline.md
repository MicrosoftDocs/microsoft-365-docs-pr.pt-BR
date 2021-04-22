---
title: Linha do tempo do evento no gerenciamento de ameaças e vulnerabilidades
description: A linha do tempo do evento é um feed de notícias de risco que ajuda você a interpretar como o risco é introduzido na organização e quais mitigações aconteceram para reduzi-lo.
keywords: linha do tempo do evento, linha do tempo do evento do Microsoft Defender for Endpoint, linha do tempo do evento tvm do Microsoft Defender para Endpoint, gerenciamento de ameaças e vulnerabilidades, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933476"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="8c5c6-104">Linha do tempo do evento - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8c5c6-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8c5c6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c5c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c5c6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8c5c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8c5c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c5c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8c5c6-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8c5c6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c5c6-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="8c5c6-110">A linha do tempo do evento é um feed de notícias de risco que ajuda você a interpretar como o risco é introduzido na organização por meio de novas vulnerabilidades ou explorações.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="8c5c6-111">Você pode exibir eventos que podem afetar o risco da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="8c5c6-112">Por exemplo, você pode encontrar novas vulnerabilidades que foram introduzidas, vulnerabilidades que se tornaram exploradas, exploração que foi adicionada a um kit de exploração e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="8c5c6-113">A linha do tempo [](tvm-exposure-score.md) do evento também conta a história da sua pontuação de exposição e da Pontuação Segura da Microsoft para [Dispositivos](tvm-microsoft-secure-score-devices.md) para que você possa determinar a causa de grandes alterações.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="8c5c6-114">Os eventos podem afetar seus dispositivos ou sua pontuação para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="8c5c6-115">Reduza a exposição abordando o que precisa ser remediado com base nas recomendações de [segurança priorizadas.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c6-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="8c5c6-116">Para obter emails sobre novos eventos de vulnerabilidade, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c6-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="8c5c6-117">Navegue até a página linha do tempo do evento</span><span class="sxs-lookup"><span data-stu-id="8c5c6-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="8c5c6-118">Há também três pontos de entrada do painel de gerenciamento de ameaças [e vulnerabilidades:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c6-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="8c5c6-119">**Cartão de pontuação de** exposição da organização : passe o mouse sobre os pontos de evento no gráfico "Pontuação de Exposição ao longo do tempo" e selecione "Ver todos os eventos deste dia".</span><span class="sxs-lookup"><span data-stu-id="8c5c6-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="8c5c6-120">Os eventos representam vulnerabilidades de software.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="8c5c6-121">**Pontuação segura da Microsoft para dispositivos**: passe o mouse sobre os pontos de evento no gráfico "Sua pontuação para dispositivos ao longo do tempo" e selecione "Ver todos os eventos deste dia".</span><span class="sxs-lookup"><span data-stu-id="8c5c6-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="8c5c6-122">Os eventos representam novas avaliações de configuração.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="8c5c6-123">**Cartão de eventos principais**: Selecione "Mostrar mais" na parte inferior da tabela de eventos principais.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="8c5c6-124">O cartão exibe os três eventos mais impactados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="8c5c6-125">Eventos impactáveis podem incluir se o evento afetar um grande número de dispositivos ou se for uma vulnerabilidade crítica.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="8c5c6-126">Pontuação de exposição e Pontuação Segura da Microsoft para Dispositivos gráficos</span><span class="sxs-lookup"><span data-stu-id="8c5c6-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="8c5c6-127">No painel de gerenciamento de ameaças e vulnerabilidades, passe o mouse sobre o gráfico de pontuação de exposição para exibir os principais eventos de vulnerabilidade de software desse dia que afetaram seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="8c5c6-128">Passe o mouse sobre o gráfico Microsoft Secure Score for Devices para exibir novas avaliações de configuração de segurança que afetam sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="8c5c6-129">Se não houver eventos que afetem seus dispositivos ou sua pontuação para dispositivos, nenhum será mostrado.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="8c5c6-130">![Foco de pontuação de ](images/tvm-event-timeline-exposure-score350.png) 
 ![ exposição Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="8c5c6-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="8c5c6-131">Detalhar até eventos desse dia</span><span class="sxs-lookup"><span data-stu-id="8c5c6-131">Drill down to events from that day</span></span>

<span data-ttu-id="8c5c6-132">Selecionar **Mostrar todos os eventos deste dia** leva você à página linha do tempo do evento com um intervalo de datas personalizado para esse dia.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Intervalo de datas personalizado selecionado da linha do tempo do evento](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="8c5c6-134">Selecione **Intervalo personalizado** para alterar o intervalo de datas para outro personalizado ou um intervalo de tempo pré-definido.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Opções de intervalo de datas da linha do tempo do evento](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="8c5c6-136">Visão geral da linha do tempo do evento</span><span class="sxs-lookup"><span data-stu-id="8c5c6-136">Event timeline overview</span></span>

<span data-ttu-id="8c5c6-137">Na página Linha do tempo do evento, você pode exibir todas as informações necessárias relacionadas a um evento.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="8c5c6-138">Recursos:</span><span class="sxs-lookup"><span data-stu-id="8c5c6-138">Features:</span></span>

- <span data-ttu-id="8c5c6-139">Personalizar colunas</span><span class="sxs-lookup"><span data-stu-id="8c5c6-139">Customize columns</span></span>
- <span data-ttu-id="8c5c6-140">Filtrar por tipo de evento ou por cento de dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="8c5c6-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="8c5c6-141">Exibir 30, 50 ou 100 itens por página</span><span class="sxs-lookup"><span data-stu-id="8c5c6-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="8c5c6-142">Os dois números grandes na parte superior da página mostram o número de novas vulnerabilidades e vulnerabilidades exploráveis, não eventos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="8c5c6-143">Alguns eventos podem ter várias vulnerabilidades e algumas vulnerabilidades podem ter vários eventos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Página da linha do tempo do evento](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="8c5c6-145">Colunas</span><span class="sxs-lookup"><span data-stu-id="8c5c6-145">Columns</span></span>

- <span data-ttu-id="8c5c6-146">**Data**: mês, dia, ano</span><span class="sxs-lookup"><span data-stu-id="8c5c6-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="8c5c6-147">**Evento**: evento impactante, incluindo componente, tipo e número de dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="8c5c6-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="8c5c6-148">**Componente relacionado**: software</span><span class="sxs-lookup"><span data-stu-id="8c5c6-148">**Related component**: software</span></span>
- <span data-ttu-id="8c5c6-149">**Dispositivos originalmente afetados**: o número e a porcentagem de dispositivos afetados quando esse evento ocorreu originalmente.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="8c5c6-150">Você também pode filtrar pela porcentagem de dispositivos originalmente afetados, do número total de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="8c5c6-151">**Dispositivos atualmente afetados**: o número atual e porcentagem de dispositivos que esse evento afeta no momento.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="8c5c6-152">Você pode encontrar esse campo selecionando **Personalizar colunas**.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="8c5c6-153">**Tipos**: refletem eventos marcados por hora que impactam a pontuação.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="8c5c6-154">Eles podem ser filtrados.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-154">They can be filtered.</span></span>
    - <span data-ttu-id="8c5c6-155">Exploit adicionado a um kit de exploração</span><span class="sxs-lookup"><span data-stu-id="8c5c6-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="8c5c6-156">Exploit foi verificado</span><span class="sxs-lookup"><span data-stu-id="8c5c6-156">Exploit was verified</span></span>
    - <span data-ttu-id="8c5c6-157">Nova exploração pública</span><span class="sxs-lookup"><span data-stu-id="8c5c6-157">New public exploit</span></span>
    - <span data-ttu-id="8c5c6-158">Nova vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="8c5c6-158">New vulnerability</span></span>
    - <span data-ttu-id="8c5c6-159">Nova avaliação de configuração</span><span class="sxs-lookup"><span data-stu-id="8c5c6-159">New configuration assessment</span></span>
- <span data-ttu-id="8c5c6-160">**Tendência de pontuação**: tendência de pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="8c5c6-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="8c5c6-161">Ícones</span><span class="sxs-lookup"><span data-stu-id="8c5c6-161">Icons</span></span>

<span data-ttu-id="8c5c6-162">Os ícones a seguir aparecem ao lado de eventos:</span><span class="sxs-lookup"><span data-stu-id="8c5c6-162">The following icons show up next to events:</span></span>

- ![ícone de bug](images/tvm-black-bug-icon.png) <span data-ttu-id="8c5c6-164">Nova exploração pública</span><span class="sxs-lookup"><span data-stu-id="8c5c6-164">New public exploit</span></span>
- ![ícone de aviso de relatório](images/report-warning-icon.png) <span data-ttu-id="8c5c6-166">Nova vulnerabilidade foi publicada</span><span class="sxs-lookup"><span data-stu-id="8c5c6-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="8c5c6-168">Exploit encontrado no kit de exploração</span><span class="sxs-lookup"><span data-stu-id="8c5c6-168">Exploit found in exploit kit</span></span>
- ![ícone de bug com ícone de aviso](images/bug-caution-icon2.png) <span data-ttu-id="8c5c6-170">Explorar verificado</span><span class="sxs-lookup"><span data-stu-id="8c5c6-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="8c5c6-171">Fazer uma análise de um evento específico</span><span class="sxs-lookup"><span data-stu-id="8c5c6-171">Drill down to a specific event</span></span>

<span data-ttu-id="8c5c6-172">Depois de selecionar um evento, um flyout aparecerá com uma lista de detalhes e CVEs atuais que afetam seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="8c5c6-173">Você pode mostrar mais CVEs ou exibir a recomendação relacionada.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="8c5c6-174">A seta abaixo de "tendência de pontuação" ajuda você a determinar se esse evento potencialmente aumentou ou baixou sua pontuação de exposição organizacional.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="8c5c6-175">Maior pontuação de exposição significa que os dispositivos são mais vulneráveis à exploração.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Flyout da linha do tempo do evento](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="8c5c6-177">A partir daí, selecione **Ir para recomendação de segurança** relacionada exibir a recomendação que aborda a nova vulnerabilidade de software na página recomendações de [segurança](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="8c5c6-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="8c5c6-178">Depois de ler a descrição e os detalhes de vulnerabilidade na recomendação de segurança, você pode enviar uma solicitação de correção e acompanhar a solicitação na página [de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c6-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="8c5c6-179">Exibir cronogramas de eventos em páginas de software</span><span class="sxs-lookup"><span data-stu-id="8c5c6-179">View Event timelines in software pages</span></span>

<span data-ttu-id="8c5c6-180">Para abrir uma página de software, selecione um evento > selecione o nome do software hiperlink (como Visual Studio 2017) na seção chamada "Componente relacionado" no flyout.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="8c5c6-181">Saiba mais sobre páginas de software</span><span class="sxs-lookup"><span data-stu-id="8c5c6-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="8c5c6-182">Uma página completa aparecerá com todos os detalhes de um software específico.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="8c5c6-183">Passe o mouse sobre o gráfico para ver a linha do tempo dos eventos para esse software específico.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Página de software com um gráfico de linha do tempo do evento](images/tvm-event-timeline-software2.png)

<span data-ttu-id="8c5c6-185">Navegue até a guia linha do tempo do evento para exibir todos os eventos relacionados a esse software.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="8c5c6-186">Você também pode ver recomendações de segurança, vulnerabilidades descobertas, dispositivos instalados e distribuição de versão.</span><span class="sxs-lookup"><span data-stu-id="8c5c6-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Página de software com uma guia linha do tempo do evento](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="8c5c6-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8c5c6-188">Related topics</span></span>

- [<span data-ttu-id="8c5c6-189">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8c5c6-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8c5c6-190">Painel</span><span class="sxs-lookup"><span data-stu-id="8c5c6-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="8c5c6-191">Pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="8c5c6-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="8c5c6-192">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="8c5c6-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="8c5c6-193">Correção de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8c5c6-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="8c5c6-194">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="8c5c6-194">Software inventory</span></span>](tvm-software-inventory.md)

