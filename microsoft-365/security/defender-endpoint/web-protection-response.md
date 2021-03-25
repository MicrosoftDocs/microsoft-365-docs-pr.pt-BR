---
title: Responder a ameaças da Web no Microsoft Defender ATP
description: Responder a alertas relacionados a sites mal-intencionados e indesejados. Entenda como a proteção contra ameaças da Web informa os usuários finais por meio de seus navegadores da Web e notificações do Windows
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, alertas, resposta, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web, notificações, usuários finais, notificações do Windows, página de bloqueio,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9f3873db4f85cec3f5f1a400dcfb7930c6a4faa
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187536"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="583a1-105">Responder a ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="583a1-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="583a1-106">**Applies to:**</span></span>
- [<span data-ttu-id="583a1-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="583a1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="583a1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="583a1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="583a1-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="583a1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="583a1-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="583a1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="583a1-111">A proteção da Web no Microsoft Defender para Ponto de Extremidade permite investigar e responder com eficiência a alertas relacionados a sites mal-intencionados e sites em sua lista de indicadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="583a1-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="583a1-112">Exibir alertas de ameaça da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-112">View web threat alerts</span></span>
<span data-ttu-id="583a1-113">O Microsoft Defender para Ponto de Extremidade gera os seguintes [alertas](manage-alerts.md) para atividades da Web mal-intencionadas ou suspeitas:</span><span class="sxs-lookup"><span data-stu-id="583a1-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="583a1-114">**Conexão suspeita bloqueada pela** proteção de rede — esse alerta é gerado quando uma  tentativa de acessar um site mal-intencionado ou um site em sua lista de indicadores personalizados é interrompida pela proteção de rede no modo *de* bloqueio</span><span class="sxs-lookup"><span data-stu-id="583a1-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="583a1-115">**Conexão suspeita detectada** pela proteção de rede — esse alerta é gerado quando uma tentativa de acessar um site mal-intencionado ou um site em sua lista de indicadores personalizados é detectada pela proteção de rede no modo somente *auditoria*</span><span class="sxs-lookup"><span data-stu-id="583a1-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="583a1-116">Cada alerta fornece as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="583a1-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="583a1-117">Dispositivo que tentou acessar o site bloqueado</span><span class="sxs-lookup"><span data-stu-id="583a1-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="583a1-118">Aplicativo ou programa usado para enviar a solicitação da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="583a1-119">URL ou URL mal-intencionadas na lista de indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="583a1-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="583a1-120">Ações recomendadas para respondentes</span><span class="sxs-lookup"><span data-stu-id="583a1-120">Recommended actions for responders</span></span>

![Imagem de um alerta relacionado à proteção contra ameaças da Web](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="583a1-122">Para reduzir o volume de alertas, o Microsoft Defender for Endpoint consolida detecções de ameaças da Web para o mesmo domínio no mesmo dispositivo todos os dias para um único alerta.</span><span class="sxs-lookup"><span data-stu-id="583a1-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="583a1-123">Somente um alerta é gerado e contado no [relatório de proteção da Web.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="583a1-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="583a1-124">Inspecionar detalhes do site</span><span class="sxs-lookup"><span data-stu-id="583a1-124">Inspect website details</span></span>
<span data-ttu-id="583a1-125">Você pode mergulhar mais fundo selecionando a URL ou o domínio do site no alerta.</span><span class="sxs-lookup"><span data-stu-id="583a1-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="583a1-126">Isso abre uma página sobre essa URL ou domínio específico com várias informações, incluindo:</span><span class="sxs-lookup"><span data-stu-id="583a1-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="583a1-127">Dispositivos que tentaram acessar o site</span><span class="sxs-lookup"><span data-stu-id="583a1-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="583a1-128">Incidentes e alertas relacionados ao site</span><span class="sxs-lookup"><span data-stu-id="583a1-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="583a1-129">A frequência com que o site foi visto em eventos em sua organização</span><span class="sxs-lookup"><span data-stu-id="583a1-129">How frequent the website was seen in events in your organization</span></span>

    ![Imagem da página de detalhes do domínio ou da entidade URL](images/wtp-website-details.png)

[<span data-ttu-id="583a1-131">Saiba mais sobre páginas de URL ou entidade de domínio</span><span class="sxs-lookup"><span data-stu-id="583a1-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="583a1-132">Inspecionar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="583a1-132">Inspect the device</span></span>
<span data-ttu-id="583a1-133">Você também pode verificar o dispositivo que tentou acessar uma URL bloqueada.</span><span class="sxs-lookup"><span data-stu-id="583a1-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="583a1-134">Selecionar o nome do dispositivo na página de alerta abre uma página com informações abrangentes sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="583a1-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="583a1-135">Saiba mais sobre páginas de entidade de dispositivo</span><span class="sxs-lookup"><span data-stu-id="583a1-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="583a1-136">Navegador da Web e notificações do Windows para usuários finais</span><span class="sxs-lookup"><span data-stu-id="583a1-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="583a1-137">Com a proteção da Web no Microsoft Defender para Ponto de Extremidade, seus usuários finais serão impedidos de visitar sites mal-intencionados ou indesejados usando o Microsoft Edge ou outros navegadores.</span><span class="sxs-lookup"><span data-stu-id="583a1-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="583a1-138">Como o bloqueio é realizado pela proteção [de rede,](network-protection.md)eles verão um erro genérico do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="583a1-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="583a1-139">Eles também verão uma notificação do Windows.</span><span class="sxs-lookup"><span data-stu-id="583a1-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="583a1-140">![Imagem do Microsoft Edge mostrando um erro 403 e a ameaça web de notificação do Windows ](images/wtp-browser-blocking-page.png)
 *bloqueada no Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="583a1-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="583a1-141">![Imagem do navegador da Web do Chrome mostrando um aviso de conexão segura e a ameaça web de notificação do Windows ](images/wtp-chrome-browser-blocking-page.png)
 *bloqueada no Chrome*</span><span class="sxs-lookup"><span data-stu-id="583a1-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="583a1-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="583a1-142">Related topics</span></span>
- [<span data-ttu-id="583a1-143">Visão geral da proteção da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="583a1-144">Filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="583a1-145">Proteção contra ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="583a1-146">Monitorar a segurança da Web</span><span class="sxs-lookup"><span data-stu-id="583a1-146">Monitor web security</span></span>](web-protection-monitoring.md)
