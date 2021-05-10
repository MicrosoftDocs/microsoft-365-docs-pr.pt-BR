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
ms.openlocfilehash: 5ea847e822e094049dd8f0b941f22f3bb4f7eff4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297171"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="a290e-104">Introdução à resposta ao seu primeiro incidente</span><span class="sxs-lookup"><span data-stu-id="a290e-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a290e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a290e-105">**Applies to:**</span></span>
- <span data-ttu-id="a290e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a290e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a290e-107">A estratégia de resposta a incidentes de uma organização determina sua capacidade de lidar com incidentes de segurança cada vez mais disruptivos e crimes cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="a290e-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="a290e-108">Ao tomar medidas preventivas é importante, a capacidade de agir rapidamente para conter, erradicar e recuperar de incidentes detectados pode minimizar danos e perdas comerciais.</span><span class="sxs-lookup"><span data-stu-id="a290e-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="a290e-109">Este passo a passo da resposta a incidentes mostra como você, como parte de uma equipe de operações de segurança, pode executar a maioria das principais etapas de resposta a incidentes no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a290e-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="a290e-110">Estas são as etapas:</span><span class="sxs-lookup"><span data-stu-id="a290e-110">Here are the steps:</span></span>

- <span data-ttu-id="a290e-111">Preparação da postura de segurança</span><span class="sxs-lookup"><span data-stu-id="a290e-111">Preparation of your security posture</span></span>
- <span data-ttu-id="a290e-112">Para cada incidente:</span><span class="sxs-lookup"><span data-stu-id="a290e-112">For each incident:</span></span>
  - <span data-ttu-id="a290e-113">Etapa 1: Triagem e análise</span><span class="sxs-lookup"><span data-stu-id="a290e-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="a290e-114">Etapa 2: Correção (contenção, erradicação e recuperação)</span><span class="sxs-lookup"><span data-stu-id="a290e-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="a290e-115">Etapa 3: Revisão pós-incidente</span><span class="sxs-lookup"><span data-stu-id="a290e-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="a290e-116">Um incidente de segurança é definido pelo Instituto Nacional de Padrões e Tecnologia (NIST) como "uma ocorrência que, na verdade ou potencialmente, compromete a confidencialidade, a integridade ou a disponibilidade de um sistema de informações; ou as informações que o sistema processa, armazena ou transmite; ou que constitui uma violação ou ameaça iminente de violação de políticas de segurança, procedimentos de segurança ou políticas de uso aceitáveis."</span><span class="sxs-lookup"><span data-stu-id="a290e-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="a290e-117">Incidentes no Microsoft 365 Defender são os pontos de partida lógicos para análise e resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="a290e-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="a290e-118">A análise e a correção de incidentes normalmente comm a maioria das tarefas de uma equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="a290e-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="a290e-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a290e-119">Next step</span></span>

<span data-ttu-id="a290e-120">[![Preparar sua organização e Microsoft 365 locatário](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="a290e-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="a290e-121">Certifique-se de que sua organização e Microsoft 365 locatário [esteja preparado para o tratamento de incidentes.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="a290e-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a290e-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="a290e-122">See also</span></span>

<span data-ttu-id="a290e-123">Diretrizes de resposta a incidentes para Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="a290e-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="a290e-124">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="a290e-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a290e-125">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a290e-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a290e-126">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="a290e-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="a290e-127">Exemplos adicionais de primeiras respostas a incidentes:</span><span class="sxs-lookup"><span data-stu-id="a290e-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="a290e-128">Email de phishing</span><span class="sxs-lookup"><span data-stu-id="a290e-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="a290e-129">Ataque de base de identidade</span><span class="sxs-lookup"><span data-stu-id="a290e-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="a290e-130">Playbooks de resposta a incidentes detalhados</span><span class="sxs-lookup"><span data-stu-id="a290e-130">Detailed incident response playbooks</span></span>](https://docs.microsoft.com/security/compass/incident-response-playbooks)


