---
title: Introdução à resposta ao seu primeiro incidente
description: Noções básicas de resposta ao seu primeiro incidente no Microsoft 365 Defender.
keywords: incidentes, alertas, investigação, correlação, ataque, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365, resposta a incidentes, ataques cibernéticos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114501"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="d7329-104">Introdução à resposta ao seu primeiro incidente</span><span class="sxs-lookup"><span data-stu-id="d7329-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d7329-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d7329-105">**Applies to:**</span></span>
- <span data-ttu-id="d7329-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7329-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d7329-107">A estratégia de resposta a incidentes de uma organização determina sua capacidade de lidar com incidentes de segurança cada vez mais disruptivos e crimes cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="d7329-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="d7329-108">Ao tomar medidas preventivas é importante, a capacidade de agir rapidamente para conter, erradicar e recuperar de incidentes detectados pode minimizar danos e perdas comerciais.</span><span class="sxs-lookup"><span data-stu-id="d7329-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="d7329-109">Este passo a passo da resposta a incidentes mostra como você, como parte de uma equipe de operações de segurança, pode executar a maioria das principais etapas de resposta a incidentes no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d7329-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="d7329-110">Estas são as etapas:</span><span class="sxs-lookup"><span data-stu-id="d7329-110">Here are the steps:</span></span>

- <span data-ttu-id="d7329-111">Preparação da postura de segurança</span><span class="sxs-lookup"><span data-stu-id="d7329-111">Preparation of your security posture</span></span>
- <span data-ttu-id="d7329-112">Para cada incidente:</span><span class="sxs-lookup"><span data-stu-id="d7329-112">For each incident:</span></span>
  - <span data-ttu-id="d7329-113">Etapa 1: Triagem e análise</span><span class="sxs-lookup"><span data-stu-id="d7329-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="d7329-114">Etapa 2: Correção (contenção, erradicação e recuperação)</span><span class="sxs-lookup"><span data-stu-id="d7329-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="d7329-115">Etapa 3: Revisão pós-incidente</span><span class="sxs-lookup"><span data-stu-id="d7329-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="d7329-116">Um incidente de segurança é definido pelo Instituto Nacional de Padrões e Tecnologia (NIST) como "uma ocorrência que, na verdade ou potencialmente, compromete a confidencialidade, a integridade ou a disponibilidade de um sistema de informações; ou as informações que o sistema processa, armazena ou transmite; ou que constitui uma violação ou ameaça iminente de violação de políticas de segurança, procedimentos de segurança ou políticas de uso aceitáveis."</span><span class="sxs-lookup"><span data-stu-id="d7329-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="d7329-117">Incidentes no Microsoft 365 Defender são os pontos de partida lógicos para análise e resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="d7329-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="d7329-118">A análise e a correção de incidentes normalmente comm a maioria das tarefas de uma equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="d7329-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7329-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d7329-119">Next step</span></span>

<span data-ttu-id="d7329-120">[![Preparar sua organização e Microsoft 365 locatário](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="d7329-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="d7329-121">Certifique-se de que sua organização e Microsoft 365 locatário [esteja preparado para o tratamento de incidentes.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="d7329-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7329-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="d7329-122">See also</span></span>

- [<span data-ttu-id="d7329-123">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="d7329-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d7329-124">Analisar os incidentes</span><span class="sxs-lookup"><span data-stu-id="d7329-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d7329-125">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="d7329-125">Manage incidents</span></span>](manage-incidents.md)
