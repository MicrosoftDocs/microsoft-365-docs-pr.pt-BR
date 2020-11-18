---
title: Resumindo seus resultados do projeto do Microsoft 365 defender piloto
description: Conclua seu projeto piloto do Microsoft 365 defender preenchendo o Scorecard, analisando suas descobertas de relatórios e decidindo como mover para frente.
keywords: Piloto de proteção contra ameaças da Microsoft, decida o que fazer após o projeto piloto de proteção contra ameaças da Microsoft, o que fazer depois de avaliar a proteção contra ameaças da Microsoft em produção, transição do Microsoft Threat Protection Pilot para implantação, segurança da CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130908"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="7ab37-104">Fechar e resumir seu piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7ab37-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ab37-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7ab37-105">**Applies to:**</span></span>
- <span data-ttu-id="7ab37-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ab37-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="7ab37-107">[![Planejamento](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7ab37-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="7ab37-108">Planejamento</span><span class="sxs-lookup"><span data-stu-id="7ab37-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="7ab37-109">[![Preparar](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7ab37-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="7ab37-110">Preparação</span><span class="sxs-lookup"><span data-stu-id="7ab37-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="7ab37-111">[![Simular ameaças](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="7ab37-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="7ab37-112">Simular ameaças</span><span class="sxs-lookup"><span data-stu-id="7ab37-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Fechar e resumir](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="7ab37-114">Fechar e resumir</span><span class="sxs-lookup"><span data-stu-id="7ab37-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="7ab37-115">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="7ab37-115">*You are here!*</span></span>|


<span data-ttu-id="7ab37-116">Você está atualmente na fase de fechamento e resumo.</span><span class="sxs-lookup"><span data-stu-id="7ab37-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="7ab37-117">Você acabou de executar uma simulação avançada de ataque somente de memória que executou o código remotamente em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="7ab37-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="7ab37-118">Você viu como o Microsoft defender for Endpoint e o Microsoft defender para identidade detectam e criam alertas sobre atividades mal-intencionadas fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="7ab37-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="7ab37-119">Você também viu como os alertas de fontes diferentes são entregues junto com outras informações contextuais em um único incidente no portal da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab37-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7ab37-120">A integração desse tipo permite que analistas do SOC investiguem e tomem a ação necessária.</span><span class="sxs-lookup"><span data-stu-id="7ab37-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="7ab37-121">Você também criou uma consulta de busca avançada que identificará emails de entrada onde o usuário abriu ou salvou o anexo e criou a detecção com base nessa consulta.</span><span class="sxs-lookup"><span data-stu-id="7ab37-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="7ab37-122">Você atingiu o final do processo após todos os testes terem concluído.</span><span class="sxs-lookup"><span data-stu-id="7ab37-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="7ab37-123">A saída final deve ser:</span><span class="sxs-lookup"><span data-stu-id="7ab37-123">The final output should be:</span></span>

- <span data-ttu-id="7ab37-124">Um scorecard concluído</span><span class="sxs-lookup"><span data-stu-id="7ab37-124">A completed scorecard</span></span>
- <span data-ttu-id="7ab37-125">Um relatório detalhado das conclusões do piloto</span><span class="sxs-lookup"><span data-stu-id="7ab37-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="7ab37-126">Uma decisão sobre como mover para frente</span><span class="sxs-lookup"><span data-stu-id="7ab37-126">A decision on how to move forward</span></span>

<span data-ttu-id="7ab37-127">Apresente os relatórios de sua saída final para os participantes internos (identificados durante a fase de [preparação](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) e contatos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ab37-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="7ab37-128">Tal esforço garante que qualquer feedback possa ser usado para melhorar os produtos e a documentação.</span><span class="sxs-lookup"><span data-stu-id="7ab37-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="7ab37-129">Esperamos que você tenha aproveitado essa simulação.</span><span class="sxs-lookup"><span data-stu-id="7ab37-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="7ab37-130">Comece a implementar o que você aprendeu em uma escala maior em sua organização para aproveitar ao máximo a solução de segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="7ab37-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ab37-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7ab37-131">Next step</span></span>
<span data-ttu-id="7ab37-132">Saiba mais sobre os pilares do Microsoft 365 defender por meio dos seguintes guias interativos:</span><span class="sxs-lookup"><span data-stu-id="7ab37-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="7ab37-133">Proteger sua organização com o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7ab37-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="7ab37-134">Detecção de atividades suspeitas e possíveis ataques com o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="7ab37-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="7ab37-135">Detectar ameaças e gerenciar alertas com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="7ab37-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="7ab37-136">Investigue e corrija ameaças com o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7ab37-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
