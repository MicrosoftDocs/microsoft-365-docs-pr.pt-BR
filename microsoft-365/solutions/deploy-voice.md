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
description: Saiba como escolher e implantar a solução de voz correta do Teams para sua organização.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580884"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="69165-103">Planejar e implantar uma solução de voz para o Teams</span><span class="sxs-lookup"><span data-stu-id="69165-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="69165-104">Uma solução de voz do Teams permite que as pessoas em sua organização façam chamadas dentro e fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="69165-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="69165-105">Uma solução de voz completa consiste no Teams, no Sistema de Telefonia Microsoft e em uma opção de opções para se conectar à Rede Telefônica Pública Comutado (PSTN).</span><span class="sxs-lookup"><span data-stu-id="69165-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Visão geral das soluções de voz do Teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="69165-107">O Sistema de Telefonia fornece recursos completos de PBX (Central Privada de Comutamento) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="69165-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="69165-108">As chamadas entre usuários em sua organização , independentemente de sua localização geográfica, são tratadas internamente no Sistema de Telefonia, removendo assim os custos de longa distância nessas chamadas internas.</span><span class="sxs-lookup"><span data-stu-id="69165-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="69165-109">Ao conectar o Sistema de Telefonia à Rede Telefônica Pública Comuada (PSTN), os usuários do Teams também podem fazer chamadas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="69165-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="69165-110">Este guia de solução ajuda você a:</span><span class="sxs-lookup"><span data-stu-id="69165-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="69165-111">Escolha a solução de voz adequada para sua organização</span><span class="sxs-lookup"><span data-stu-id="69165-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="69165-112">Implantar a solução de voz selecionada</span><span class="sxs-lookup"><span data-stu-id="69165-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="69165-113">Siga estas etapas para escolher, planejar e configurar sua solução de voz:</span><span class="sxs-lookup"><span data-stu-id="69165-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Escolher a solução de voz](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="69165-115">Escolher a solução de voz</span><span class="sxs-lookup"><span data-stu-id="69165-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="69165-116">Configurar o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="69165-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="69165-117">Para configurar a conectividade PSTN, escolha uma das seguintes combinações:</span><span class="sxs-lookup"><span data-stu-id="69165-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="69165-118">[Plano de](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) Chamada - solução tudo na nuvem da Microsoft com a Microsoft como sua operadora PSTN</span><span class="sxs-lookup"><span data-stu-id="69165-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="69165-119">[Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Usar o Roteamento Direto para conectar sua própria operadora PSTN ao Teams</span><span class="sxs-lookup"><span data-stu-id="69165-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="69165-120">Além disso, talvez você queira ler sobre como uma grande corporação multinacional migrou para uma solução de voz do Teams no estudo de caso [contoso.](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="69165-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="69165-121">Para obter informações sobre licenças necessárias, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69165-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="69165-122">Licenças de complemento do Teams</span><span class="sxs-lookup"><span data-stu-id="69165-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="69165-123">Requisitos de licenciamento de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="69165-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
