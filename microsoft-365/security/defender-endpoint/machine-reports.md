---
title: Relatório de conformidade e saúde do dispositivo no Microsoft Defender ATP
description: Rastrear detecções de estado de saúde do dispositivo, status do antivírus, plataforma do sistema operacional e versões do Windows 10 usando o relatório de conformidade e saúde do dispositivo
keywords: estado de saúde, antivírus, plataforma do sistema operacional, versão do windows 10, versão, saúde, conformidade, estado
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
ms.openlocfilehash: 5229ba068672035c2dce3afee1919f9c2d7f9e44
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186444"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="cb474-104">Relatório de conformidade e saúde do dispositivo no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb474-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cb474-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cb474-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb474-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb474-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb474-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb474-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="cb474-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cb474-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb474-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cb474-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cb474-110">O relatório de status dos dispositivos fornece informações de alto nível sobre os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb474-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="cb474-111">O relatório inclui informações de tendência mostrando o estado de saúde do sensor, o status do antivírus, as plataformas do sistema operacional e as versões do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cb474-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="cb474-112">O painel é estruturado em duas seções: ![ Imagem do relatório do dispositivo](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="cb474-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="cb474-113">Seção</span><span class="sxs-lookup"><span data-stu-id="cb474-113">Section</span></span> | <span data-ttu-id="cb474-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb474-114">Description</span></span>
:---|:---
<span data-ttu-id="cb474-115">1</span><span class="sxs-lookup"><span data-stu-id="cb474-115">1</span></span> | <span data-ttu-id="cb474-116">Tendências de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cb474-116">Device trends</span></span>
<span data-ttu-id="cb474-117">2</span><span class="sxs-lookup"><span data-stu-id="cb474-117">2</span></span> | <span data-ttu-id="cb474-118">Resumo do dispositivo (dia atual)</span><span class="sxs-lookup"><span data-stu-id="cb474-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="cb474-119">Tendências de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cb474-119">Device trends</span></span> 
<span data-ttu-id="cb474-120">Por padrão, as tendências do dispositivo exibem informações do dispositivo do período de 30 dias que terminam no último dia completo.</span><span class="sxs-lookup"><span data-stu-id="cb474-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="cb474-121">Para obter uma perspectiva melhor sobre as tendências que ocorrem em sua organização, você pode ajustar o período de relatório ajustando o período de tempo mostrado.</span><span class="sxs-lookup"><span data-stu-id="cb474-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="cb474-122">Para ajustar o período de tempo, selecione um intervalo de tempo nas opções listadas:</span><span class="sxs-lookup"><span data-stu-id="cb474-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="cb474-123">30 dias</span><span class="sxs-lookup"><span data-stu-id="cb474-123">30 days</span></span>
- <span data-ttu-id="cb474-124">3 meses</span><span class="sxs-lookup"><span data-stu-id="cb474-124">3 months</span></span>
- <span data-ttu-id="cb474-125">6 meses</span><span class="sxs-lookup"><span data-stu-id="cb474-125">6 months</span></span>
- <span data-ttu-id="cb474-126">Personalizado</span><span class="sxs-lookup"><span data-stu-id="cb474-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="cb474-127">Esses filtros só são aplicados na seção tendências do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cb474-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="cb474-128">Ele não afeta a seção resumo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cb474-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="cb474-129">Resumo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cb474-129">Device summary</span></span> 
<span data-ttu-id="cb474-130">Embora as tendências de dispositivos mostrem informações de dispositivos tendências, o resumo do dispositivo mostra as informações do dispositivo com escopo até o dia atual.</span><span class="sxs-lookup"><span data-stu-id="cb474-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="cb474-131">Os dados refletidos na seção resumo são escopos para 180 dias antes da data atual.</span><span class="sxs-lookup"><span data-stu-id="cb474-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="cb474-132">Por exemplo, se a data de hoje for 27 de março de 2019, os dados da seção de resumo refletirão números a partir de 28 de setembro de 2018 a 27 de março de 2019.</span><span class="sxs-lookup"><span data-stu-id="cb474-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="cb474-133">O filtro aplicado na seção tendências não é aplicado na seção resumo.</span><span class="sxs-lookup"><span data-stu-id="cb474-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="cb474-134">A seção tendências do dispositivo permite detalhar a lista de dispositivos com o filtro correspondente aplicado a ela.</span><span class="sxs-lookup"><span data-stu-id="cb474-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="cb474-135">Por exemplo, clicar na barra Inativa no cartão de estado de estado do sensor levará a lista de dispositivos com resultados mostrando apenas dispositivos cujo status do sensor está inativo.</span><span class="sxs-lookup"><span data-stu-id="cb474-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="cb474-136">Atributos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cb474-136">Device attributes</span></span>
<span data-ttu-id="cb474-137">O relatório é feito de cartões que exibem os seguintes atributos de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="cb474-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="cb474-138">**Estado de** saúde : mostra informações sobre o estado do sensor em dispositivos, fornecendo uma exibição agregada de dispositivos que estão ativos, com comunicações prejudicadas, inativas ou onde nenhum dado do sensor é visto.</span><span class="sxs-lookup"><span data-stu-id="cb474-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="cb474-139">**Status do antivírus para dispositivos Windows 10** ativos : mostra o número de dispositivos e o status do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="cb474-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="cb474-140">**Plataformas do sistema operacional**: mostra a distribuição de plataformas do sistema operacional existentes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb474-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="cb474-141">**Versões do Windows 10**: mostra a distribuição de dispositivos Windows 10 e suas versões em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb474-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="cb474-142">Filtrar dados</span><span class="sxs-lookup"><span data-stu-id="cb474-142">Filter data</span></span>
 
<span data-ttu-id="cb474-143">Use os filtros fornecidos para incluir ou excluir dispositivos com determinados atributos.</span><span class="sxs-lookup"><span data-stu-id="cb474-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="cb474-144">Você pode selecionar vários filtros para aplicar a partir dos atributos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cb474-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="cb474-145">Esses filtros se aplicam **a** todos os cartões do relatório.</span><span class="sxs-lookup"><span data-stu-id="cb474-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="cb474-146">Por exemplo, para mostrar dados sobre dispositivos Windows 10 com estado de saúde do sensor ativo:</span><span class="sxs-lookup"><span data-stu-id="cb474-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="cb474-147">Em **Filtros > estado de saúde do sensor > Ativo**.</span><span class="sxs-lookup"><span data-stu-id="cb474-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="cb474-148">Em seguida, **selecione plataformas do sistema operacional > Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="cb474-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="cb474-149">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cb474-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="cb474-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cb474-150">Related topic</span></span>
- [<span data-ttu-id="cb474-151">Relatório de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="cb474-151">Threat protection report</span></span>](threat-protection-reports.md)
