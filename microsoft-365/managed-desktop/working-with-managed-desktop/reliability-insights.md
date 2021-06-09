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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739751"
---
# <a name="reliability-insights"></a><span data-ttu-id="7c370-103">Percepções de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="7c370-103">Reliability insights</span></span>

<span data-ttu-id="7c370-104">Esta exibição fornece um resumo de saúde de seus dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="7c370-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="7c370-105">Para exibir dados de confiabilidade, selecione a guia **Confiabilidade.**</span><span class="sxs-lookup"><span data-stu-id="7c370-105">To view reliability data, select the **Reliability** tab.</span></span>


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade ao longo do gráfico de tempo no canto superior direito, tabela de problemas superiores na parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="7c370-108">A **seção Confiabilidade** entre dispositivos oferece um resumo rápido da sua implantação nos últimos 14 dias informando a porcentagem de dispositivos considerados "saudáveis" e o tempo média observado desde a última falha relatada.</span><span class="sxs-lookup"><span data-stu-id="7c370-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="7c370-109">O **gráfico De confiabilidade** ao longo do tempo à direita relata o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="7c370-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="7c370-110">A **seção Principais problemas** detalha problemas detectados específicos que afetam pelo menos 5% dos dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="7c370-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="7c370-111">Os detalhes relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="7c370-111">Reported details include:</span></span>

- <span data-ttu-id="7c370-112">O tipo de problema</span><span class="sxs-lookup"><span data-stu-id="7c370-112">The type of issue</span></span>
    - <span data-ttu-id="7c370-113">Falhas no aplicativo, em que um aplicativo para de funcionar ou para inesperadamente</span><span class="sxs-lookup"><span data-stu-id="7c370-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="7c370-114">O aplicativo trava, onde um aplicativo para de responder à entrada</span><span class="sxs-lookup"><span data-stu-id="7c370-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="7c370-115">Erros críticos, que ocorrem quando Windows encontrou um problema do qual não pode se recuperar</span><span class="sxs-lookup"><span data-stu-id="7c370-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="7c370-116">O número de dispositivos afetados pelo mesmo problema</span><span class="sxs-lookup"><span data-stu-id="7c370-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="7c370-117">A porcentagem de dispositivos gerenciados que o número representa</span><span class="sxs-lookup"><span data-stu-id="7c370-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="7c370-118">A contagem total de ocorrências do problema específico</span><span class="sxs-lookup"><span data-stu-id="7c370-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="7c370-119">O componente de software que parece ser a origem do problema</span><span class="sxs-lookup"><span data-stu-id="7c370-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="7c370-120">A categoria do problema detectado:</span><span class="sxs-lookup"><span data-stu-id="7c370-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="7c370-121">Navegador (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="7c370-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="7c370-122">Desconhecido (componentes que não são da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="7c370-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="7c370-123">Driver (áudio, gráficos ou outros drivers)</span><span class="sxs-lookup"><span data-stu-id="7c370-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="7c370-124">Produtividade (Slack, G-Suites, Microsoft Office e seus complementos ou extensões, Teams)</span><span class="sxs-lookup"><span data-stu-id="7c370-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="7c370-125">Mídia (aplicativos de imagem, música ou vídeo</span><span class="sxs-lookup"><span data-stu-id="7c370-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="7c370-126">Segurança (Windows de segurança)</span><span class="sxs-lookup"><span data-stu-id="7c370-126">Security (Windows security components)</span></span>
- <span data-ttu-id="7c370-127">O status atual como Área de Trabalho Gerenciada da Microsoft Operações investiga e correção do problema</span><span class="sxs-lookup"><span data-stu-id="7c370-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

