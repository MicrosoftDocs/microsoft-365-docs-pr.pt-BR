---
title: Insights de bateria
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 81b7a7c3db69d1c20f9a9cd8c6ea4a37b481ce59
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269382"
---
# <a name="battery-insights"></a><span data-ttu-id="447ea-103">Insights de bateria</span><span class="sxs-lookup"><span data-stu-id="447ea-103">Battery insights</span></span>
<span data-ttu-id="447ea-104">Este modo de exibição fornece métricas de energia, bateria e uso do aplicativo para seus dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="447ea-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="447ea-105">Para esses fins, um aplicativo é considerado "em uso" se estiver em execução e em foco.</span><span class="sxs-lookup"><span data-stu-id="447ea-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="447ea-106">Para exibir os dados de uso, selecione a guia **bateria** .</span><span class="sxs-lookup"><span data-stu-id="447ea-106">To view usage data, select the **Battery** tab.</span></span>

![Painel da bateria: vida prevista da bateria por modelo de dispositivo no canto superior esquerdo, os principais consumidores de energia (por aplicativo) na parte superior direita, a tabela insights na parte inferior.](images/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="447ea-109">Vida prevista da bateria</span><span class="sxs-lookup"><span data-stu-id="447ea-109">Predicted battery life</span></span>

<span data-ttu-id="447ea-110">Na área de **vida prevista da bateria** , fornecemos previsões para a vida útil esperada da bateria para seus dispositivos, organizadas por um modelo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="447ea-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="447ea-111">Esses dados são derivados de amostragem de uso de energia, tempo de uso e capacidade da bateria de uma <em>seleção</em> aleatória de dispositivos em sua implantação de área de trabalho gerenciada da Microsoft que também estão relatando dados.</span><span class="sxs-lookup"><span data-stu-id="447ea-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="447ea-112">A tabela fornece a duração prevista da bateria (em horas), a duração média da bateria para os mesmos modelos em outras implantações de área de trabalho gerenciada pela Microsoft e o número de dispositivos que relatam esses dados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="447ea-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="447ea-113">Classifique os dados selecionando os títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="447ea-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="447ea-114">Principais consumidores de energia</span><span class="sxs-lookup"><span data-stu-id="447ea-114">Top energy consumers</span></span>

<span data-ttu-id="447ea-115">Na área de **consumidores de energia superior** , você encontrará os aplicativos em seu ambiente que consomem mais energia em milliWatt-hours (MWh).</span><span class="sxs-lookup"><span data-stu-id="447ea-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="447ea-116">Os aplicativos mostrados são por dispositivo específico, que você seleciona na seção **vida útil da bateria prevista** para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="447ea-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="447ea-117">Por exemplo, para ver o consumo por aplicativo para seus dispositivos do catálogo de superfície 2 do Microsft, selecione essa linha na área de vida da bateria.</span><span class="sxs-lookup"><span data-stu-id="447ea-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="447ea-118">Se você não selecionar nenhum modelo, os dados de consumo do aplicativo mostrados serão para todos os aplicativos que têm dados para o coletivamente.</span><span class="sxs-lookup"><span data-stu-id="447ea-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="447ea-119">Para cada aplicativo, os segmentos coloridos mostram a distribuição do uso de energia do aplicativo entre estas categorias:</span><span class="sxs-lookup"><span data-stu-id="447ea-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="447ea-120">CPU</span><span class="sxs-lookup"><span data-stu-id="447ea-120">CPU</span></span>
- <span data-ttu-id="447ea-121">Exibir</span><span class="sxs-lookup"><span data-stu-id="447ea-121">Display</span></span>
- <span data-ttu-id="447ea-122">Rede</span><span class="sxs-lookup"><span data-stu-id="447ea-122">Network</span></span>
- <span data-ttu-id="447ea-123">Outros</span><span class="sxs-lookup"><span data-stu-id="447ea-123">Other</span></span>

<span data-ttu-id="447ea-124">"Outros" podem incluir consumo de energia por uma variedade de fontes, como atividade de disco, uso de banda larga móvel e energia perdida para resistência interna.</span><span class="sxs-lookup"><span data-stu-id="447ea-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="447ea-125">Você pode filtrar esse modo de exibição para mostrar apenas aplicativos de primeiro plano, aplicativos de segundo plano ou ambos, usando o menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="447ea-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="447ea-126">Os aplicativos de primeiro plano são aqueles que tiveram a interação do usuário nos últimos 28 dias, como selecionar algo com um mouse.</span><span class="sxs-lookup"><span data-stu-id="447ea-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="447ea-127">Informações</span><span class="sxs-lookup"><span data-stu-id="447ea-127">Insights</span></span>

<span data-ttu-id="447ea-128">A área do **insights** mostra os três principais consumidores de energia nas categorias CPU e rede.</span><span class="sxs-lookup"><span data-stu-id="447ea-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="447ea-129">Esses itens estão consumindo mais do que a média de energia em comparação com todas as implantações do Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="447ea-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="447ea-130">Não mostramos o recurso de exibição porque depende muito do tempo de uso do dispositivo e das configurações de brilho da tela.</span><span class="sxs-lookup"><span data-stu-id="447ea-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="447ea-131">Selecione as listagens na coluna **detalhes** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="447ea-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="447ea-132">Otimização da bateria</span><span class="sxs-lookup"><span data-stu-id="447ea-132">Battery optimization</span></span>

<span data-ttu-id="447ea-133">O Windows 10 oferece numerosas [configurações de dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para melhorar o uso de energia e aumentar a duração da bateria de seus dispositivos de área de trabalho gerenciados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="447ea-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="447ea-134">Algumas dessas configurações podem reduzir outras funcionalidades do Windows, portanto, você também precisará considerar outros fatores como a função do dispositivo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="447ea-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="447ea-135">O suporte do Windows mantém uma lista dessas [dicas de economia de bateria](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="447ea-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="447ea-136">Os usuários podem ajustar algumas configurações por conta própria, sem a necessidade de elevação ou suporte de administrador.</span><span class="sxs-lookup"><span data-stu-id="447ea-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="447ea-137">Outras configurações exigem suporte do administrador de ti da sua organização.</span><span class="sxs-lookup"><span data-stu-id="447ea-137">Other settings require support from your organization's IT administrator.</span></span>
