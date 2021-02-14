---
title: Percepções da bateria
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529834"
---
# <a name="battery-insights"></a><span data-ttu-id="d5727-103">Percepções da bateria</span><span class="sxs-lookup"><span data-stu-id="d5727-103">Battery insights</span></span>
<span data-ttu-id="d5727-104">Essa exibição fornece métricas de uso de energia, bateria e aplicativos para seus dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5727-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d5727-105">Para essas finalidades, um aplicativo é considerado "em uso" se estiver em execução e em foco.</span><span class="sxs-lookup"><span data-stu-id="d5727-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="d5727-106">Para exibir dados de uso, selecione a **guia** Bateria.</span><span class="sxs-lookup"><span data-stu-id="d5727-106">To view usage data, select the **Battery** tab.</span></span>

![Painel de bateria: duração prevista da bateria por modelo de dispositivo no canto superior esquerdo, principais consumidores de energia (por aplicativo) no canto superior direito, tabela insights na parte inferior.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="d5727-109">Duração prevista da bateria</span><span class="sxs-lookup"><span data-stu-id="d5727-109">Predicted battery life</span></span>

<span data-ttu-id="d5727-110">Na área **de duração prevista da bateria,** fornecemos previsões para a duração esperada da bateria para seus dispositivos, organizadas por modelo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5727-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="d5727-111">Esses dados são derivados do uso de energia de <em></em> amostragem, do tempo de uso e da capacidade da bateria de uma seleção aleatória dos dispositivos em sua implantação da Área de Trabalho Gerenciada da Microsoft que também estão relatando dados.</span><span class="sxs-lookup"><span data-stu-id="d5727-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="d5727-112">A tabela fornece a duração prevista da bateria (em horas), a duração média da bateria para os mesmos modelos em outras implantações da Área de Trabalho Gerenciada da Microsoft e o número de dispositivos que relatam esses dados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d5727-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="d5727-113">Classificar os dados selecionando os títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="d5727-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="d5727-114">Principais consumidores de energia</span><span class="sxs-lookup"><span data-stu-id="d5727-114">Top energy consumers</span></span>

<span data-ttu-id="d5727-115">Na área **Principais consumidores de** energia, você encontrará os aplicativos em seu ambiente que consomem mais energia em miliKw-hours (mWh).</span><span class="sxs-lookup"><span data-stu-id="d5727-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="d5727-116">Os aplicativos mostrados são por dispositivo específico, que você seleciona na seção **Duração** prevista da bateria à esquerda.</span><span class="sxs-lookup"><span data-stu-id="d5727-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="d5727-117">Por exemplo, para ver o consumo por aplicativo para seus dispositivos Microsoft Surface Book 2, selecione essa linha na área de duração da bateria.</span><span class="sxs-lookup"><span data-stu-id="d5727-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="d5727-118">Se você não selecionar qualquer modelo, os dados de consumo de aplicativo mostrados são para todos os aplicativos para os quais temos dados coletivamente.</span><span class="sxs-lookup"><span data-stu-id="d5727-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="d5727-119">Para cada aplicativo, os segmentos coloridos mostram a distribuição do uso de energia do aplicativo entre essas categorias:</span><span class="sxs-lookup"><span data-stu-id="d5727-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="d5727-120">CPU</span><span class="sxs-lookup"><span data-stu-id="d5727-120">CPU</span></span>
- <span data-ttu-id="d5727-121">Display</span><span class="sxs-lookup"><span data-stu-id="d5727-121">Display</span></span>
- <span data-ttu-id="d5727-122">Rede</span><span class="sxs-lookup"><span data-stu-id="d5727-122">Network</span></span>
- <span data-ttu-id="d5727-123">Outros</span><span class="sxs-lookup"><span data-stu-id="d5727-123">Other</span></span>

<span data-ttu-id="d5727-124">"Outros" podem incluir o consumo de energia por várias fontes, como atividade de disco, uso de banda larga móvel e energia perdida para resistência interna.</span><span class="sxs-lookup"><span data-stu-id="d5727-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="d5727-125">Você pode filtrar essa exibição para mostrar somente aplicativos em primeiro plano, aplicativos em segundo plano ou ambos usando o menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="d5727-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="d5727-126">Os aplicativos em primeiro plano são aqueles que tiveram interação do usuário nos últimos 28 dias, como selecionar algo com um mouse.</span><span class="sxs-lookup"><span data-stu-id="d5727-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="d5727-127">Insights</span><span class="sxs-lookup"><span data-stu-id="d5727-127">Insights</span></span>

<span data-ttu-id="d5727-128">A **área Insights** mostra os três principais consumidores de energia nas categorias de CPU e rede.</span><span class="sxs-lookup"><span data-stu-id="d5727-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="d5727-129">Esses itens estão consumindo energia superior à média em comparação com todas as implantações da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5727-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="d5727-130">Não mostramos o recurso de exibição porque ele depende muito do tempo de uso do dispositivo e das configurações de brilho da tela.</span><span class="sxs-lookup"><span data-stu-id="d5727-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="d5727-131">Selecione as listagem na coluna **Detalhes** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d5727-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="d5727-132">Otimização de bateria</span><span class="sxs-lookup"><span data-stu-id="d5727-132">Battery optimization</span></span>

<span data-ttu-id="d5727-133">O Windows 10 oferece várias configurações de dispositivo para melhorar o uso de energia e aumentar a duração da bateria dos [dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5727-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d5727-134">Algumas dessas configurações podem diminuir outras funcionalidades do Windows, portanto, você também terá que considerar outros fatores, como a função do dispositivo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d5727-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="d5727-135">O suporte do Windows mantém uma lista dessas dicas [de economia de bateria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="d5727-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="d5727-136">Os usuários podem ajustar algumas configurações por conta própria sem a necessidade de elevação ou suporte do administrador.</span><span class="sxs-lookup"><span data-stu-id="d5727-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="d5727-137">Outras configurações exigem suporte do administrador de IT da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d5727-137">Other settings require support from your organization's IT administrator.</span></span>
