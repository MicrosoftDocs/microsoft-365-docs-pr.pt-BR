---
title: Monitorando a segurança de navegação na Web no Microsoft Defender para Ponto de Extremidade
description: Usar a proteção da Web no Microsoft Defender para Ponto de Extremidade para monitorar a segurança da navegação na Web
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, monitoramento, relatórios, cartões, lista de domínios, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687418"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="848a7-104">Monitorar a segurança de navegação na Web</span><span class="sxs-lookup"><span data-stu-id="848a7-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="848a7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="848a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="848a7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="848a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="848a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="848a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="848a7-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="848a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="848a7-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="848a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="848a7-110">A proteção da Web permite monitorar a segurança de navegação na Web da sua organização por meio de relatórios em Relatórios > **Proteção Da Web** no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="848a7-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="848a7-111">O relatório contém cartões que fornecem estatísticas de detecção de ameaças da Web.</span><span class="sxs-lookup"><span data-stu-id="848a7-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="848a7-112">**Detecções** de proteção contra ameaças da Web ao longo do tempo - esse cartão de tendência exibe o número de ameaças da Web detectadas por tipo durante o período de tempo selecionado (Últimos 30 dias, Últimos 3 meses, Últimos 6 meses)</span><span class="sxs-lookup"><span data-stu-id="848a7-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Imagem do cartão mostrando detecções de proteção contra ameaças da Web ao longo do tempo](images/wtp-blocks-over-time.png)

- <span data-ttu-id="848a7-114">**Resumo da proteção contra** ameaças da Web - esse cartão exibe o total de detecções de ameaças da Web nos últimos 30 dias, mostrando a distribuição entre os diferentes tipos de ameaças à Web.</span><span class="sxs-lookup"><span data-stu-id="848a7-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="848a7-115">Selecionar uma fatia abre a lista dos domínios encontrados com sites mal-intencionados ou indesejados.</span><span class="sxs-lookup"><span data-stu-id="848a7-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Imagem do cartão mostrando resumo de proteção contra ameaças da Web](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="848a7-117">Pode levar até 12 horas antes que um bloco seja refletido nos cartões ou na lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="848a7-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="848a7-118">Tipos de ameaças à Web</span><span class="sxs-lookup"><span data-stu-id="848a7-118">Types of web threats</span></span>

<span data-ttu-id="848a7-119">A proteção da Web categoriza sites mal-intencionados e indesejados como:</span><span class="sxs-lookup"><span data-stu-id="848a7-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="848a7-120">**Phishing** - sites que contêm formulários web falsos e outros mecanismos de phishing projetados para enganar os usuários para divulgar credenciais e outras informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="848a7-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="848a7-121">**Mal-intencionado** - sites que hospedam malware e exploram código</span><span class="sxs-lookup"><span data-stu-id="848a7-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="848a7-122">**Indicador personalizado** - sites cujas URLs ou domínios você adicionou à sua lista [de indicadores personalizados](manage-indicators.md) para bloqueio</span><span class="sxs-lookup"><span data-stu-id="848a7-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="848a7-123">Exibir a lista de domínios</span><span class="sxs-lookup"><span data-stu-id="848a7-123">View the domain list</span></span>

<span data-ttu-id="848a7-124">Selecione uma categoria de ameaça da Web específica no cartão de resumo de proteção contra ameaças da **Web** para abrir a **página Domínios.**</span><span class="sxs-lookup"><span data-stu-id="848a7-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="848a7-125">Esta página exibe a lista dos domínios sob essa categoria de ameaça.</span><span class="sxs-lookup"><span data-stu-id="848a7-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="848a7-126">A página fornece as seguintes informações para cada domínio:</span><span class="sxs-lookup"><span data-stu-id="848a7-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="848a7-127">**Contagem de** acesso - número de solicitações para URLs no domínio</span><span class="sxs-lookup"><span data-stu-id="848a7-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="848a7-128">**Blocos** - número de vezes que as solicitações foram bloqueadas</span><span class="sxs-lookup"><span data-stu-id="848a7-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="848a7-129">**Tendência de acesso** - alteração no número de tentativas de acesso</span><span class="sxs-lookup"><span data-stu-id="848a7-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="848a7-130">**Categoria de ameaça** - tipo de ameaça da Web</span><span class="sxs-lookup"><span data-stu-id="848a7-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="848a7-131">**Dispositivos** - número de dispositivos com tentativas de acesso</span><span class="sxs-lookup"><span data-stu-id="848a7-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="848a7-132">Selecione um domínio para exibir a lista de dispositivos que tentaram acessar URLs nesse domínio e a lista de URLs.</span><span class="sxs-lookup"><span data-stu-id="848a7-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="848a7-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="848a7-133">Related topics</span></span>

- [<span data-ttu-id="848a7-134">Visão geral da proteção da Web</span><span class="sxs-lookup"><span data-stu-id="848a7-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="848a7-135">Filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="848a7-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="848a7-136">Proteção contra ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="848a7-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="848a7-137">Responder a ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="848a7-137">Respond to web threats</span></span>](web-protection-response.md)
