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
# <a name="reliability-insights"></a><span data-ttu-id="13929-103">Percepções de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="13929-103">Reliability insights</span></span>

<span data-ttu-id="13929-104">Esta exibição fornece um resumo de saúde de seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="13929-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="13929-105">Para exibir dados de confiabilidade, selecione a **guia** Confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="13929-105">To view reliability data, select the **Reliability** tab.</span></span>


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade ao longo do tempo gráfico no canto superior direito, tabela de problemas superior na parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="13929-108">A seção **Confiabilidade** entre dispositivos oferece um resumo rápido da sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados " health" e o tempo média observado desde a última falha relatada.</span><span class="sxs-lookup"><span data-stu-id="13929-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="13929-109">O **gráfico Confiabilidade ao** longo do tempo à direita relata o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="13929-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="13929-110">A **seção Principais problemas** detalha problemas detectados específicos que afetam pelo menos 5% de seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="13929-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="13929-111">Os detalhes relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="13929-111">Reported details include:</span></span>

- <span data-ttu-id="13929-112">O tipo de problema</span><span class="sxs-lookup"><span data-stu-id="13929-112">The type of issue</span></span>
    - <span data-ttu-id="13929-113">O aplicativo falha, em que um aplicativo para de funcionar ou para inesperadamente</span><span class="sxs-lookup"><span data-stu-id="13929-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="13929-114">O aplicativo trava, onde um aplicativo para de responder à entrada</span><span class="sxs-lookup"><span data-stu-id="13929-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="13929-115">Erros críticos, que ocorrem quando o Windows encontra um problema do qual ele não pode se recuperar</span><span class="sxs-lookup"><span data-stu-id="13929-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="13929-116">O número de dispositivos afetados pelo mesmo problema</span><span class="sxs-lookup"><span data-stu-id="13929-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="13929-117">A porcentagem de dispositivos gerenciados que o número representa</span><span class="sxs-lookup"><span data-stu-id="13929-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="13929-118">A contagem total de ocorrências do problema específico</span><span class="sxs-lookup"><span data-stu-id="13929-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="13929-119">O componente de software que parece ser a origem do problema</span><span class="sxs-lookup"><span data-stu-id="13929-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="13929-120">A categoria do problema detectado:</span><span class="sxs-lookup"><span data-stu-id="13929-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="13929-121">Navegador (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="13929-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="13929-122">Desconhecido (componentes que não são da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="13929-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="13929-123">Driver (áudio, elementos gráficos ou outros drivers)</span><span class="sxs-lookup"><span data-stu-id="13929-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="13929-124">Produtividade (Slack, G-Suites, Microsoft Office e seus complementos ou extensões, Teams)</span><span class="sxs-lookup"><span data-stu-id="13929-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="13929-125">Mídia (aplicativos de imagem, música ou vídeo</span><span class="sxs-lookup"><span data-stu-id="13929-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="13929-126">Segurança (componentes de segurança do Windows)</span><span class="sxs-lookup"><span data-stu-id="13929-126">Security (Windows security components)</span></span>
- <span data-ttu-id="13929-127">O status atual como Operações da Área de Trabalho Gerenciada da Microsoft investiga e corre o problema</span><span class="sxs-lookup"><span data-stu-id="13929-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

