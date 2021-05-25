---
title: Etapa 3. Executar uma revisão pós-incidente do seu primeiro incidente
description: Como executar uma revisão do seu primeiro incidente no Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
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
ms.openlocfilehash: 6b5311a2923d7b299ba4f70ef3c2e8d91809e7c8
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651363"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="d5781-105">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="d5781-105">Step 3.</span></span> <span data-ttu-id="d5781-106">Executar uma revisão pós-incidente do seu primeiro incidente</span><span class="sxs-lookup"><span data-stu-id="d5781-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d5781-107">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d5781-107">**Applies to:**</span></span>
- <span data-ttu-id="d5781-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5781-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5781-109">O Instituto Nacional de Padrões e Tecnologia (NIST) recomenda que, uma vez que todas as etapas tenham sido tomadas para se recuperar do ataque, as organizações devem revisar o incidente para aprender com ele e melhorar a postura ou os processos de segurança.</span><span class="sxs-lookup"><span data-stu-id="d5781-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and improve security posture or processes.</span></span> <span data-ttu-id="d5781-110">A avaliação dos diferentes aspectos da manipulação de incidentes torna-se importante na preparação para o próximo incidente.</span><span class="sxs-lookup"><span data-stu-id="d5781-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="d5781-111">Microsoft 365 O Defender pode ajudar na execução de atividades pós-incidentes fornecendo a uma organização alertas que se alinham ao [MITRE ATT](https://attack.mitre.org/)&CK Framework .</span><span class="sxs-lookup"><span data-stu-id="d5781-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="d5781-112">Todos os ataques de rótulo de soluções do Microsoft Defender de acordo com uma técnica ou tática&CK da ATT.</span><span class="sxs-lookup"><span data-stu-id="d5781-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="d5781-113">Ao mapear alertas para essa estrutura do setor, você pode:</span><span class="sxs-lookup"><span data-stu-id="d5781-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="d5781-114">Conduzir uma análise de lacunas na cobertura de segurança.</span><span class="sxs-lookup"><span data-stu-id="d5781-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="d5781-115">Determinar a atribuição de campanha e adversário.</span><span class="sxs-lookup"><span data-stu-id="d5781-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="d5781-116">Execute a análise de tendência.</span><span class="sxs-lookup"><span data-stu-id="d5781-116">Perform trend analysis.</span></span>
- <span data-ttu-id="d5781-117">Identificar lacunas de habilidades na conscientização do método de ataque.</span><span class="sxs-lookup"><span data-stu-id="d5781-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="d5781-118">Crie um Power Automate Playbook para correção mais rápida.</span><span class="sxs-lookup"><span data-stu-id="d5781-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="d5781-119">A atividade de revisão pós-incidente também pode resultar em ajustar a configuração de segurança e os processos da equipe de segurança, aprimorando os recursos de resposta da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d5781-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5781-120">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d5781-120">Next step</span></span>

<span data-ttu-id="d5781-121">Consulte estes caminhos de investigação adicionais:</span><span class="sxs-lookup"><span data-stu-id="d5781-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="d5781-122">Email de phishing</span><span class="sxs-lookup"><span data-stu-id="d5781-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="d5781-123">Ataque baseado em identidade</span><span class="sxs-lookup"><span data-stu-id="d5781-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="d5781-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="d5781-124">See also</span></span>

- [<span data-ttu-id="d5781-125">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="d5781-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d5781-126">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="d5781-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d5781-127">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="d5781-127">Manage incidents</span></span>](manage-incidents.md)
