---
title: Percepções de confiabilidade
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950337"
---
# <a name="reliability-insights"></a><span data-ttu-id="b0b77-103">Percepções de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="b0b77-103">Reliability insights</span></span>

<span data-ttu-id="b0b77-104">Este modo de exibição fornece um resumo de integridade dos dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="b0b77-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="b0b77-105">Para exibir os dados de confiabilidade, selecione a guia **confiabilidade** .</span><span class="sxs-lookup"><span data-stu-id="b0b77-105">To view reliability data, select the **Reliability** tab.</span></span>


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade através do gráfico de tempo no canto superior direito, principais problemas na parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="b0b77-108">A seção **confiabilidade entre dispositivos** oferece um resumo de integridade rápida de sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados como "saudáveis" e o tempo médio observado desde a última falha relatada.</span><span class="sxs-lookup"><span data-stu-id="b0b77-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="b0b77-109">O gráfico de **confiabilidade ao longo do tempo** indica o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="b0b77-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="b0b77-110">A seção **principais problemas** detalha os problemas detectados específicos que afetam pelo menos 5% dos seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="b0b77-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="b0b77-111">Os detalhes relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="b0b77-111">Reported details include:</span></span>

- <span data-ttu-id="b0b77-112">O tipo de problema</span><span class="sxs-lookup"><span data-stu-id="b0b77-112">The type of issue</span></span>
    - <span data-ttu-id="b0b77-113">O aplicativo falha, no qual um aplicativo para de funcionar ou pára inesperadamente</span><span class="sxs-lookup"><span data-stu-id="b0b77-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="b0b77-114">O aplicativo paralisa, onde um aplicativo pára de responder à entrada</span><span class="sxs-lookup"><span data-stu-id="b0b77-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="b0b77-115">Erros críticos, que ocorrem quando o Windows encontrou um problema que não pode se recuperar de</span><span class="sxs-lookup"><span data-stu-id="b0b77-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="b0b77-116">O número de dispositivos afetados pelo mesmo problema</span><span class="sxs-lookup"><span data-stu-id="b0b77-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="b0b77-117">A porcentagem de dispositivos gerenciados que o número representa</span><span class="sxs-lookup"><span data-stu-id="b0b77-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="b0b77-118">A contagem total de ocorrências do problema específico</span><span class="sxs-lookup"><span data-stu-id="b0b77-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="b0b77-119">O componente de software que parece ser a origem do problema</span><span class="sxs-lookup"><span data-stu-id="b0b77-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="b0b77-120">A categoria do problema detectado:</span><span class="sxs-lookup"><span data-stu-id="b0b77-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="b0b77-121">Navegador (borda, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="b0b77-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="b0b77-122">Desconhecido (componentes não Microsoft)</span><span class="sxs-lookup"><span data-stu-id="b0b77-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="b0b77-123">Driver (áudio, gráficos ou outros drivers)</span><span class="sxs-lookup"><span data-stu-id="b0b77-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="b0b77-124">Produtividade (margem de atraso, pacotes G-Suites, Microsoft Office e seus complementos ou extensões, equipes)</span><span class="sxs-lookup"><span data-stu-id="b0b77-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="b0b77-125">Mídia (imagem, música ou aplicativos de vídeo</span><span class="sxs-lookup"><span data-stu-id="b0b77-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="b0b77-126">Segurança (componentes de segurança do Windows)</span><span class="sxs-lookup"><span data-stu-id="b0b77-126">Security (Windows security components)</span></span>
- <span data-ttu-id="b0b77-127">O status atual como operações de área de trabalho gerenciada da Microsoft investiga e corrige o problema</span><span class="sxs-lookup"><span data-stu-id="b0b77-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

