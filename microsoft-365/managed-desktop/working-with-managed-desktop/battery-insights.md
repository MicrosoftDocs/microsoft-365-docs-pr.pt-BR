---
title: Percepções da bateria
description: Um relatório que mostra dados sobre a duração prevista da bateria e os principais consumidores de energia
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739754"
---
# <a name="battery-insights"></a><span data-ttu-id="dc332-104">Percepções da bateria</span><span class="sxs-lookup"><span data-stu-id="dc332-104">Battery insights</span></span>
<span data-ttu-id="dc332-105">Essa exibição fornece métricas de uso de energia, bateria e aplicativos para seus Área de Trabalho Gerenciada da Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc332-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dc332-106">Para esses fins, um aplicativo é considerado "em uso" se estiver em execução e em foco.</span><span class="sxs-lookup"><span data-stu-id="dc332-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="dc332-107">Para exibir dados de uso, selecione a **guia Bateria.**</span><span class="sxs-lookup"><span data-stu-id="dc332-107">To view usage data, select the **Battery** tab.</span></span>

![Painel de bateria: vida da bateria prevista por modelo de dispositivo na parte superior esquerda, principais consumidores de energia (por aplicativo) no canto superior direito, tabela insights na parte inferior.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="dc332-110">Duração prevista da bateria</span><span class="sxs-lookup"><span data-stu-id="dc332-110">Predicted battery life</span></span>

<span data-ttu-id="dc332-111">Na área **Duração prevista da** bateria, fornecemos previsões para a duração esperada da bateria para seus dispositivos, organizada por modelo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc332-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="dc332-112">Esses dados são derivados do uso de energia de <em></em> amostragem, tempo de uso e capacidade de bateria de uma seleção aleatória dos dispositivos em sua implantação Área de Trabalho Gerenciada da Microsoft que também estão relatando dados.</span><span class="sxs-lookup"><span data-stu-id="dc332-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="dc332-113">A tabela fornece a duração prevista da bateria (em horas), a duração média da bateria para os mesmos modelos em outras implantações Área de Trabalho Gerenciada da Microsoft e o número de dispositivos que relatam esses dados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="dc332-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="dc332-114">Classificar os dados selecionando os títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="dc332-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="dc332-115">Principais consumidores de energia</span><span class="sxs-lookup"><span data-stu-id="dc332-115">Top energy consumers</span></span>

<span data-ttu-id="dc332-116">Na área **Principais consumidores de** energia, você encontrará os aplicativos em seu ambiente que consomem mais energia em miliWatt-horas (mWh).</span><span class="sxs-lookup"><span data-stu-id="dc332-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="dc332-117">Os aplicativos mostrados são por dispositivo específico, que você seleciona na seção **Vida útil** da bateria prevista à esquerda.</span><span class="sxs-lookup"><span data-stu-id="dc332-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="dc332-118">Por exemplo, para ver o consumo por aplicativo para seus dispositivos Microsoft Surface Book 2, selecione essa linha na área de vida da bateria.</span><span class="sxs-lookup"><span data-stu-id="dc332-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="dc332-119">Se você não selecionar nenhum modelo, os dados de consumo de aplicativo mostrados serão para todos os aplicativos para os quais temos dados coletivamente.</span><span class="sxs-lookup"><span data-stu-id="dc332-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="dc332-120">Para cada aplicativo, segmentos coloridos mostram a distribuição do uso de energia do aplicativo entre essas categorias:</span><span class="sxs-lookup"><span data-stu-id="dc332-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="dc332-121">CPU</span><span class="sxs-lookup"><span data-stu-id="dc332-121">CPU</span></span>
- <span data-ttu-id="dc332-122">Monitor</span><span class="sxs-lookup"><span data-stu-id="dc332-122">Display</span></span>
- <span data-ttu-id="dc332-123">Rede</span><span class="sxs-lookup"><span data-stu-id="dc332-123">Network</span></span>
- <span data-ttu-id="dc332-124">Outros</span><span class="sxs-lookup"><span data-stu-id="dc332-124">Other</span></span>

<span data-ttu-id="dc332-125">"Other" pode incluir o consumo de energia por várias fontes, como atividade em disco, uso de banda larga móvel e perda de energia para resistência interna.</span><span class="sxs-lookup"><span data-stu-id="dc332-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="dc332-126">Você pode filtrar essa exibição para mostrar somente aplicativos em primeiro plano, aplicativos em segundo plano ou ambos usando o menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="dc332-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="dc332-127">Os aplicativos em primeiro plano são aqueles que tiveram interação do usuário nos últimos 28 dias, como selecionar algo com um mouse.</span><span class="sxs-lookup"><span data-stu-id="dc332-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="dc332-128">Insights</span><span class="sxs-lookup"><span data-stu-id="dc332-128">Insights</span></span>

<span data-ttu-id="dc332-129">A **área Insights** mostra os três principais consumidores de energia nas categorias cpu e rede.</span><span class="sxs-lookup"><span data-stu-id="dc332-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="dc332-130">Esses itens estão consumindo energia superior à média em comparação com todas as Área de Trabalho Gerenciada da Microsoft implantações.</span><span class="sxs-lookup"><span data-stu-id="dc332-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="dc332-131">Não mostramos o recurso de exibição porque depende muito do tempo de uso do dispositivo e das configurações de brilho da tela.</span><span class="sxs-lookup"><span data-stu-id="dc332-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="dc332-132">Selecione os listings na coluna **Detalhes** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="dc332-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="dc332-133">Otimização de bateria</span><span class="sxs-lookup"><span data-stu-id="dc332-133">Battery optimization</span></span>

<span data-ttu-id="dc332-134">Windows 10 oferece várias configurações de dispositivo [para](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) melhorar o uso de energia e aumentar a duração da bateria de seus Área de Trabalho Gerenciada da Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc332-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dc332-135">Algumas dessas configurações podem diminuir outras funcionalidades Windows, portanto, você também terá que considerar outros fatores, como a função do dispositivo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc332-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="dc332-136">Windows suporte mantém uma lista dessas dicas [de economia de bateria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="dc332-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="dc332-137">Os usuários podem ajustar algumas configurações por conta própria sem a necessidade de elevação ou suporte do administrador.</span><span class="sxs-lookup"><span data-stu-id="dc332-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="dc332-138">Outras configurações exigem suporte do administrador de IT da sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc332-138">Other settings require support from your organization's IT administrator.</span></span>
