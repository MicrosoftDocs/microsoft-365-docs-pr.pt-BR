---
title: Insights de confiabilidade
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634028"
---
# <a name="reliability-insights"></a><span data-ttu-id="55348-103">Insights de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="55348-103">Reliability insights</span></span>

<span data-ttu-id="55348-104">Este modo de exibição fornece um resumo de integridade dos dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="55348-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="55348-105">Para exibir os dados de confiabilidade, selecione a guia **confiabilidade** .</span><span class="sxs-lookup"><span data-stu-id="55348-105">To view reliability data, select the **Reliability** tab.</span></span>


![Painel de confiabilidade](images/insights_reliability.png)

<span data-ttu-id="55348-107">A seção **confiabilidade entre dispositivos** oferece um resumo de integridade rápida de sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados como "saudáveis" e o tempo médio observado desde a última falha relatada.</span><span class="sxs-lookup"><span data-stu-id="55348-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="55348-108">O gráfico de **confiabilidade ao longo do tempo** indica o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="55348-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="55348-109">A seção **principais problemas** detalha os problemas detectados específicos que afetam pelo menos 5% dos seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="55348-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="55348-110">Os detalhes relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="55348-110">Reported details include:</span></span>

- <span data-ttu-id="55348-111">O tipo de problema</span><span class="sxs-lookup"><span data-stu-id="55348-111">The type of issue</span></span>
    - <span data-ttu-id="55348-112">O aplicativo falha, no qual um aplicativo para de funcionar ou pára inesperadamente</span><span class="sxs-lookup"><span data-stu-id="55348-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="55348-113">O aplicativo paralisa, onde um aplicativo pára de responder à entrada</span><span class="sxs-lookup"><span data-stu-id="55348-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="55348-114">Erros críticos, que ocorrem quando o Windows encontrou um problema que não pode se recuperar de</span><span class="sxs-lookup"><span data-stu-id="55348-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="55348-115">O número de dispositivos afetados pelo mesmo problema</span><span class="sxs-lookup"><span data-stu-id="55348-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="55348-116">A porcentagem de dispositivos gerenciados que o número representa</span><span class="sxs-lookup"><span data-stu-id="55348-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="55348-117">A contagem total de ocorrências do problema específico</span><span class="sxs-lookup"><span data-stu-id="55348-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="55348-118">O componente de software que parece ser a origem do problema</span><span class="sxs-lookup"><span data-stu-id="55348-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="55348-119">A categoria do problema detectado:</span><span class="sxs-lookup"><span data-stu-id="55348-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="55348-120">Navegador (borda, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="55348-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="55348-121">Desconhecido (componentes não Microsoft)</span><span class="sxs-lookup"><span data-stu-id="55348-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="55348-122">Driver (áudio, gráficos ou outros drivers)</span><span class="sxs-lookup"><span data-stu-id="55348-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="55348-123">Produtividade (margem de atraso, pacotes G-Suites, Microsoft Office e seus complementos ou extensões, equipes)</span><span class="sxs-lookup"><span data-stu-id="55348-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="55348-124">Mídia (imagem, música ou aplicativos de vídeo</span><span class="sxs-lookup"><span data-stu-id="55348-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="55348-125">Segurança (componentes de segurança do Windows)</span><span class="sxs-lookup"><span data-stu-id="55348-125">Security (Windows security components)</span></span>
- <span data-ttu-id="55348-126">O status atual como operações de área de trabalho gerenciada da Microsoft investiga e corrige o problema</span><span class="sxs-lookup"><span data-stu-id="55348-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

