---
title: Insights de confiabilidade
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085661"
---
# <a name="reliability-insights"></a><span data-ttu-id="4552f-103">Insights de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="4552f-103">Reliability insights</span></span>

<span data-ttu-id="4552f-104">Este modo de exibição fornece um resumo de integridade dos dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="4552f-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="4552f-105">Para exibir os dados de confiabilidade, selecione a guia **confiabilidade** .</span><span class="sxs-lookup"><span data-stu-id="4552f-105">To view reliability data, select the **Reliability** tab.</span></span>


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade através do gráfico de tempo no canto superior direito, principais problemas na parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="4552f-108">A seção **confiabilidade entre dispositivos** oferece um resumo de integridade rápida de sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados como "saudáveis" e o tempo médio observado desde a última falha relatada.</span><span class="sxs-lookup"><span data-stu-id="4552f-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="4552f-109">O gráfico de **confiabilidade ao longo do tempo** indica o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="4552f-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="4552f-110">A seção **principais problemas** detalha os problemas detectados específicos que afetam pelo menos 5% dos seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="4552f-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="4552f-111">Os detalhes relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="4552f-111">Reported details include:</span></span>

- <span data-ttu-id="4552f-112">O tipo de problema</span><span class="sxs-lookup"><span data-stu-id="4552f-112">The type of issue</span></span>
    - <span data-ttu-id="4552f-113">O aplicativo falha, no qual um aplicativo para de funcionar ou pára inesperadamente</span><span class="sxs-lookup"><span data-stu-id="4552f-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="4552f-114">O aplicativo paralisa, onde um aplicativo pára de responder à entrada</span><span class="sxs-lookup"><span data-stu-id="4552f-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="4552f-115">Erros críticos, que ocorrem quando o Windows encontrou um problema que não pode se recuperar de</span><span class="sxs-lookup"><span data-stu-id="4552f-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="4552f-116">O número de dispositivos afetados pelo mesmo problema</span><span class="sxs-lookup"><span data-stu-id="4552f-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="4552f-117">A porcentagem de dispositivos gerenciados que o número representa</span><span class="sxs-lookup"><span data-stu-id="4552f-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="4552f-118">A contagem total de ocorrências do problema específico</span><span class="sxs-lookup"><span data-stu-id="4552f-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="4552f-119">O componente de software que parece ser a origem do problema</span><span class="sxs-lookup"><span data-stu-id="4552f-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="4552f-120">A categoria do problema detectado:</span><span class="sxs-lookup"><span data-stu-id="4552f-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="4552f-121">Navegador (borda, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="4552f-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="4552f-122">Desconhecido (componentes não Microsoft)</span><span class="sxs-lookup"><span data-stu-id="4552f-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="4552f-123">Driver (áudio, gráficos ou outros drivers)</span><span class="sxs-lookup"><span data-stu-id="4552f-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="4552f-124">Produtividade (margem de atraso, pacotes G-Suites, Microsoft Office e seus complementos ou extensões, equipes)</span><span class="sxs-lookup"><span data-stu-id="4552f-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="4552f-125">Mídia (imagem, música ou aplicativos de vídeo</span><span class="sxs-lookup"><span data-stu-id="4552f-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="4552f-126">Segurança (componentes de segurança do Windows)</span><span class="sxs-lookup"><span data-stu-id="4552f-126">Security (Windows security components)</span></span>
- <span data-ttu-id="4552f-127">O status atual como operações de área de trabalho gerenciada da Microsoft investiga e corrige o problema</span><span class="sxs-lookup"><span data-stu-id="4552f-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

