---
title: Diretrizes de segurança da Microsoft para campanhas políticas e entidades sem fins lucrativos
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Resumo: Diretrizes de planejamento e implementação para organizações ágeis que têm um perfil de ameaça maior.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ed01d2c41529782c5c714bfe66096b97300712
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287396"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="6eae2-103">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="6eae2-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6eae2-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="6eae2-104">**Applies to**</span></span>
- [<span data-ttu-id="6eae2-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6eae2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6eae2-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6eae2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="6eae2-107">**Resumo:** Diretrizes de planejamento e implementação para organizações ágeis que têm um perfil de ameaça maior.</span><span class="sxs-lookup"><span data-stu-id="6eae2-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="6eae2-p101">Se sua organização é ágil, você tem uma pequena equipe de TI e seu perfil de ameaça é maior do que a média, estas diretrizes foram projetadas para você. Esta solução demonstra como criar rapidamente um ambiente com serviços de nuvem essenciais que incluem controles seguros desde o início. Essas diretrizes incluem as recomendações de segurança prescritiva para proteger dados, identidades, email e acesso de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="6eae2-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="6eae2-111">Diretrizes da solução de segurança</span><span class="sxs-lookup"><span data-stu-id="6eae2-111">Security solution guidance</span></span>

<span data-ttu-id="6eae2-p102">Estas diretrizes descrevem como implementar um ambiente de nuvem seguro. As diretrizes da solução podem ser usadas por qualquer organização. Isso inclui ajuda adicional para organizações ágeis com contas de convidado e acesso BYOD. Você pode usar essas diretrizes como o ponto inicial para a criação do seu ambiente. Apreciamos seus comentários em [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6eae2-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="6eae2-117">Item</span><span class="sxs-lookup"><span data-stu-id="6eae2-117">Item</span></span>|<span data-ttu-id="6eae2-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="6eae2-118">Description</span></span>|
|---|---|
|<span data-ttu-id="6eae2-119">**Diretrizes de segurança da Microsoft para campanhas políticas**</span><span class="sxs-lookup"><span data-stu-id="6eae2-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="6eae2-120">[![Miniatura para conjunto de minipôsteres.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="6eae2-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="6eae2-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="6eae2-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="6eae2-p103">Este guia usa uma organização de campanha política como exemplo. Use este guia como um ponto de partida para qualquer ambiente.</span><span class="sxs-lookup"><span data-stu-id="6eae2-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="6eae2-124">**Diretrizes de segurança da Microsoft para organizações sem fins lucrativos**</span><span class="sxs-lookup"><span data-stu-id="6eae2-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="6eae2-125">[![Imagem em miniatura para arquivos disponíveis para download](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="6eae2-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="6eae2-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="6eae2-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="6eae2-p104">Este guia é ligeiramente revisado para organizações sem fins lucrativos. Por exemplo, ele faz referência aos planos do Office 365 para entidades sem fins lucrativos. As diretrizes técnicas são as mesmas do guia de solução de campanha política.</span><span class="sxs-lookup"><span data-stu-id="6eae2-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="6eae2-130">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="6eae2-130">Test Lab Guides</span></span>

<span data-ttu-id="6eae2-131">Para criar um ambiente de desenvolvimento/teste para esta solução, siga a orientação de laboratório de teste seguinte:</span><span class="sxs-lookup"><span data-stu-id="6eae2-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="6eae2-132">Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política</span><span class="sxs-lookup"><span data-stu-id="6eae2-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="6eae2-133">Crie assinaturas de avaliação do Office 365 e EMS e, em seguida crie grupos e usuários para uma campanha política representativa.</span><span class="sxs-lookup"><span data-stu-id="6eae2-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="6eae2-134">Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="6eae2-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="6eae2-135">Crie quatro sites de equipe do SharePoint Online com os níveis de segurança Interno, Particular, Confidencial e Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="6eae2-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="6eae2-136">Confira outros recursos de segurança para demonstração ou prova de conceito em [Guias de laboratório de teste do Office 365](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="6eae2-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="6eae2-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="6eae2-137">See Also</span></span>

[<span data-ttu-id="6eae2-138">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="6eae2-138">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="6eae2-139">Recursos de arquitetura de TI do Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="6eae2-139">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
