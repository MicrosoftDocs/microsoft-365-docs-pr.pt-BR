---
title: Implantar voz em Microsoft 365
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
description: Saiba como escolher e implantar a solução de voz Teams voz correta para sua organização.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918377"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="84fbb-103">Planejar e implantar uma solução de voz para o Teams</span><span class="sxs-lookup"><span data-stu-id="84fbb-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="84fbb-104">Uma Teams de voz permite que as pessoas em sua organização façam chamadas dentro e fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="84fbb-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="84fbb-105">Uma solução de voz completa consiste em Teams, Telefone Microsoft System e uma opção de opções para se conectar à PSTN (Rede Telefônica Pública Comugada).</span><span class="sxs-lookup"><span data-stu-id="84fbb-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams visão geral das soluções de voz](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="84fbb-107">Sistema de Telefonia fornece recursos completos de Exchange (PBX) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="84fbb-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="84fbb-108">As chamadas entre usuários em sua organização, independentemente de sua localização geográfica, são tratadas internamente Sistema de Telefonia, removendo custos de longa distância nessas chamadas internas.</span><span class="sxs-lookup"><span data-stu-id="84fbb-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="84fbb-109">Ao conectar o Sistema de Telefonia à PSTN (Rede Telefônica Pública Comucionada), seus usuários Teams também podem fazer chamadas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="84fbb-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="84fbb-110">Essa orientação de solução ajuda você a:</span><span class="sxs-lookup"><span data-stu-id="84fbb-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="84fbb-111">Escolha a solução de voz ideal para sua organização</span><span class="sxs-lookup"><span data-stu-id="84fbb-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="84fbb-112">Implantar a solução de voz selecionada</span><span class="sxs-lookup"><span data-stu-id="84fbb-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="84fbb-113">Siga estas etapas para escolher, planejar e configurar sua solução de voz:</span><span class="sxs-lookup"><span data-stu-id="84fbb-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Escolher a solução de voz](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="84fbb-115">Escolher a solução de voz</span><span class="sxs-lookup"><span data-stu-id="84fbb-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="84fbb-116">Configurar o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="84fbb-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="84fbb-117">Configurar a conectividade PSTN escolhendo um, ou uma combinação, do seguinte:</span><span class="sxs-lookup"><span data-stu-id="84fbb-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="84fbb-118">[Plano de Chamada](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - a solução all-in-the-cloud da Microsoft com a Microsoft como sua operadora PSTN</span><span class="sxs-lookup"><span data-stu-id="84fbb-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="84fbb-119">[Roteamento Direto](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Roteamento Direto para conectar sua própria operadora PSTN ao Teams</span><span class="sxs-lookup"><span data-stu-id="84fbb-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="84fbb-120">Além disso, talvez você queira ler sobre como uma grande corporação multi-nacional migrou para uma solução de voz Teams no estudo de caso [contoso.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="84fbb-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="84fbb-121">Para obter informações sobre licenças necessárias, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="84fbb-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="84fbb-122">Teams licenças de complemento</span><span class="sxs-lookup"><span data-stu-id="84fbb-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="84fbb-123">Requisitos de licenciamento de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="84fbb-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)