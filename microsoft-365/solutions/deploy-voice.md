---
title: Implantar voz no Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Saiba como escolher e implantar a solução de voz da equipe certa para sua organização.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580884"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="221d5-103">Planejar e implantar uma solução de voz do teams</span><span class="sxs-lookup"><span data-stu-id="221d5-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="221d5-104">Uma solução de voz do teams permite que as pessoas em sua organização façam chamadas dentro e fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="221d5-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="221d5-105">Uma solução de voz completa consiste em Teams, sistema de telefonia da Microsoft e uma opção de opções para se conectar à PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="221d5-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Visão geral das soluções de voz do teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="221d5-107">O sistema de telefonia oferece recursos completos de PBX (central privada de comutação telefônica) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="221d5-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="221d5-108">Chamadas entre usuários em sua organização – não importa a localização geográfica--são manipuladas internamente no sistema de telefonia, removendo custos de longa distância nessas chamadas internas.</span><span class="sxs-lookup"><span data-stu-id="221d5-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="221d5-109">Ao conectar o sistema de telefonia à rede telefônica pública comutada (PSTN), seus usuários do teams também podem fazer chamadas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="221d5-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="221d5-110">Esta orientação de solução ajuda você a:</span><span class="sxs-lookup"><span data-stu-id="221d5-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="221d5-111">Escolha a solução de voz certa para a sua organização</span><span class="sxs-lookup"><span data-stu-id="221d5-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="221d5-112">Implantar a solução de voz selecionada</span><span class="sxs-lookup"><span data-stu-id="221d5-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="221d5-113">Siga estas etapas para escolher, planejar e configurar sua solução de voz:</span><span class="sxs-lookup"><span data-stu-id="221d5-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Escolha sua solução de voz](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="221d5-115">Escolha sua solução de voz</span><span class="sxs-lookup"><span data-stu-id="221d5-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="221d5-116">Configurar o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="221d5-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="221d5-117">Configure a conectividade PSTN escolhendo uma ou uma combinação das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="221d5-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="221d5-118">[Plano de chamadas](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -solução multinuvem da Microsoft com a Microsoft como sua OPERADORa PSTN</span><span class="sxs-lookup"><span data-stu-id="221d5-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="221d5-119">[Roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -use o roteamento direto para conectar sua própria operadora PSTN ao Teams</span><span class="sxs-lookup"><span data-stu-id="221d5-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="221d5-120">Além disso, você pode querer ler sobre como uma empresa multinacional de grande porte migrou para uma solução de voz do teams no [estudo de caso da Contoso](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="221d5-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="221d5-121">Para obter informações sobre as licenças necessárias, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="221d5-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="221d5-122">Licenças complementares do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="221d5-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="221d5-123">Requisitos de licenciamento direto de roteamento</span><span class="sxs-lookup"><span data-stu-id="221d5-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
