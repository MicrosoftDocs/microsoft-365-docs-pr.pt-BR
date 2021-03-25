---
title: Exibir e organizar a lista de dispositivos do Microsoft Defender ATP
description: Saiba mais sobre os recursos disponíveis que você pode usar na lista Dispositivos, como classificação, filtragem e exportação da lista para aprimorar as investigações.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
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
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185666"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="d8eda-104">Exibir e organizar a lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="d8eda-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d8eda-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d8eda-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8eda-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d8eda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8eda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8eda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8eda-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d8eda-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d8eda-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d8eda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="d8eda-110">A **lista Dispositivos** mostra uma lista dos dispositivos em sua rede onde os alertas foram gerados.</span><span class="sxs-lookup"><span data-stu-id="d8eda-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="d8eda-111">Por padrão, a fila exibe dispositivos vistos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d8eda-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="d8eda-112">Rapidamente, você verá informações como domínio, nível de risco, plataforma do sistema operacional e outros detalhes para facilitar a identificação dos dispositivos mais em risco.</span><span class="sxs-lookup"><span data-stu-id="d8eda-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="d8eda-113">Há várias opções que você pode escolher para personalizar a exibição de lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d8eda-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="d8eda-114">Na navegação superior, você pode:</span><span class="sxs-lookup"><span data-stu-id="d8eda-114">On the top navigation you can:</span></span>

- <span data-ttu-id="d8eda-115">Adicionar ou remover colunas</span><span class="sxs-lookup"><span data-stu-id="d8eda-115">Add or remove columns</span></span>
- <span data-ttu-id="d8eda-116">Exportar a lista inteira no formato CSV</span><span class="sxs-lookup"><span data-stu-id="d8eda-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="d8eda-117">Selecione o número de itens a mostrar por página</span><span class="sxs-lookup"><span data-stu-id="d8eda-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="d8eda-118">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="d8eda-118">Apply filters</span></span>

<span data-ttu-id="d8eda-119">Durante o processo de integração, a lista **Dispositivos** é gradualmente preenchida com dispositivos à medida que eles começam a relatar dados do sensor.</span><span class="sxs-lookup"><span data-stu-id="d8eda-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="d8eda-120">Use esse modo de exibição para acompanhar seus pontos de extremidade integrados conforme eles estão online ou baixar a lista de pontos de extremidade completa como um arquivo CSV para análise offline.</span><span class="sxs-lookup"><span data-stu-id="d8eda-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="d8eda-121">Se você exportar a lista de dispositivos, ela conterá todos os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8eda-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="d8eda-122">Pode levar um tempo significativo para baixar, dependendo do tamanho da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8eda-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="d8eda-123">Exportar a lista no formato CSV exibe os dados de forma não filtrada.</span><span class="sxs-lookup"><span data-stu-id="d8eda-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="d8eda-124">O arquivo CSV incluirá todos os dispositivos na organização, independentemente de qualquer filtragem aplicada no próprio exibição.</span><span class="sxs-lookup"><span data-stu-id="d8eda-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Imagem da lista de dispositivos com lista de dispositivos](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="d8eda-126">Classificar e filtrar a lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d8eda-126">Sort and filter the device list</span></span>

<span data-ttu-id="d8eda-127">Você pode aplicar os filtros a seguir para limitar a lista de alertas e obter uma exibição mais focada.</span><span class="sxs-lookup"><span data-stu-id="d8eda-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="d8eda-128">Nível de risco</span><span class="sxs-lookup"><span data-stu-id="d8eda-128">Risk level</span></span>

<span data-ttu-id="d8eda-129">O nível de risco reflete a avaliação geral de risco do dispositivo com base em uma combinação de fatores, incluindo os tipos e a gravidade dos alertas ativos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d8eda-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="d8eda-130">Resolver alertas ativos, aprovar atividades de correção e suprimir alertas subsequentes pode diminuir o nível de risco.</span><span class="sxs-lookup"><span data-stu-id="d8eda-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="d8eda-131">Nível de exposição</span><span class="sxs-lookup"><span data-stu-id="d8eda-131">Exposure level</span></span>

<span data-ttu-id="d8eda-132">O nível de exposição reflete a exposição atual do dispositivo com base no impacto acumulado de suas recomendações de segurança pendentes.</span><span class="sxs-lookup"><span data-stu-id="d8eda-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="d8eda-133">Os níveis possíveis são baixos, médios e altos.</span><span class="sxs-lookup"><span data-stu-id="d8eda-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="d8eda-134">Baixa exposição significa que seus dispositivos são menos vulneráveis de exploração.</span><span class="sxs-lookup"><span data-stu-id="d8eda-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="d8eda-135">Se o nível de exposição diz "Sem dados disponíveis", há alguns motivos pelos quais isso pode ser o caso:</span><span class="sxs-lookup"><span data-stu-id="d8eda-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="d8eda-136">O dispositivo parou de relatar por mais de 30 dias – nesse caso, ele é considerado inativo e a exposição não é calculada</span><span class="sxs-lookup"><span data-stu-id="d8eda-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="d8eda-137">Sistema operacional do dispositivo sem suporte - consulte [requisitos mínimos para o Microsoft Defender para Ponto de Extremidade](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d8eda-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="d8eda-138">Dispositivo com agente estalado (muito improvável)</span><span class="sxs-lookup"><span data-stu-id="d8eda-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="d8eda-139">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d8eda-139">OS Platform</span></span>

<span data-ttu-id="d8eda-140">Selecione apenas as plataformas do sistema operacional que você está interessado em investigar.</span><span class="sxs-lookup"><span data-stu-id="d8eda-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="d8eda-141">Estado de integridade</span><span class="sxs-lookup"><span data-stu-id="d8eda-141">Health state</span></span>

<span data-ttu-id="d8eda-142">Filtrar pelos seguintes estados de saúde do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d8eda-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="d8eda-143">**Ativo** – Dispositivos que estão relatando ativamente dados do sensor para o serviço.</span><span class="sxs-lookup"><span data-stu-id="d8eda-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="d8eda-144">**Inativo –** Dispositivos que pararam completamente de enviar sinais por mais de 7 dias.</span><span class="sxs-lookup"><span data-stu-id="d8eda-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="d8eda-145">**Configuração inconfigurada** – Dispositivos que têm comunicações prejudicadas com o serviço ou não conseguem enviar dados do sensor.</span><span class="sxs-lookup"><span data-stu-id="d8eda-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="d8eda-146">Dispositivos mal configurados ainda podem ser classificados para:</span><span class="sxs-lookup"><span data-stu-id="d8eda-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="d8eda-147">Sem dados do sensor</span><span class="sxs-lookup"><span data-stu-id="d8eda-147">No sensor data</span></span>
  - <span data-ttu-id="d8eda-148">Comunicações prejudicadas</span><span class="sxs-lookup"><span data-stu-id="d8eda-148">Impaired communications</span></span>

  <span data-ttu-id="d8eda-149">Para obter mais informações sobre como resolver problemas em dispositivos mal configurados, consulte [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span><span class="sxs-lookup"><span data-stu-id="d8eda-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="d8eda-150">Status do antivírus</span><span class="sxs-lookup"><span data-stu-id="d8eda-150">Antivirus status</span></span>

<span data-ttu-id="d8eda-151">Filtrar dispositivos pelo status do antivírus.</span><span class="sxs-lookup"><span data-stu-id="d8eda-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="d8eda-152">Aplica-se apenas a dispositivos Windows 10 ativos.</span><span class="sxs-lookup"><span data-stu-id="d8eda-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="d8eda-153">**Desabilitado** - & proteção contra ameaças está desativada.</span><span class="sxs-lookup"><span data-stu-id="d8eda-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="d8eda-154">**Not reporting** - Proteção contra & vírus não está relatando.</span><span class="sxs-lookup"><span data-stu-id="d8eda-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="d8eda-155">**Não atualizado** - a proteção contra & contra vírus não está atualizada.</span><span class="sxs-lookup"><span data-stu-id="d8eda-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="d8eda-156">Para obter mais informações, [consulte View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="d8eda-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="d8eda-157">Status de mitigação de ameaças</span><span class="sxs-lookup"><span data-stu-id="d8eda-157">Threat mitigation status</span></span>

<span data-ttu-id="d8eda-158">Para exibir dispositivos que podem ser afetados por uma determinada ameaça, selecione a ameaça no menu suspenso e selecione qual aspecto de vulnerabilidade precisa ser atenuado.</span><span class="sxs-lookup"><span data-stu-id="d8eda-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="d8eda-159">Para saber mais sobre determinadas ameaças, consulte [Análise de ameaças.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="d8eda-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="d8eda-160">Para obter informações de mitigação, consulte [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="d8eda-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="d8eda-161">Versão do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d8eda-161">Windows 10 version</span></span>

<span data-ttu-id="d8eda-162">Selecione apenas as versões do Windows 10 que você está interessado em investigar.</span><span class="sxs-lookup"><span data-stu-id="d8eda-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="d8eda-163">Marcas & Grupos</span><span class="sxs-lookup"><span data-stu-id="d8eda-163">Tags & Groups</span></span>

<span data-ttu-id="d8eda-164">Filtre a lista com base no agrupamento e marcação que você adicionou a dispositivos individuais.</span><span class="sxs-lookup"><span data-stu-id="d8eda-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="d8eda-165">Consulte [Criar e gerenciar marcas de dispositivo](machine-tags.md) e Criar e gerenciar grupos de [dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d8eda-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8eda-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8eda-166">Related topics</span></span>

- [<span data-ttu-id="d8eda-167">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="d8eda-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
