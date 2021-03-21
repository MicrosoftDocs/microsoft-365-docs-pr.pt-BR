---
title: Resumindo os resultados do projeto piloto do Microsoft 365 Defender
description: Conclua seu projeto piloto do Microsoft 365 Defender concluindo seu scorecard, analisando suas descobertas do relatório e decidindo como seguir em frente.
keywords: Piloto da Proteção contra Ameaças da Microsoft, decida o que fazer depois do projeto piloto da Proteção contra Ameaças da Microsoft, o que fazer depois de avaliar a Proteção contra Ameaças da Microsoft em produção, a transição do piloto da Proteção contra Ameaças da Microsoft para a implantação, a segurança cibernética, a ameaça persistente avançada, a segurança corporativa, dispositivos, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: f646fe7061fb0793fd9922068c9037be21a236cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920391"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="eec4b-104">Fechar e resumir seu piloto do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eec4b-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eec4b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="eec4b-105">**Applies to:**</span></span>
- <span data-ttu-id="eec4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eec4b-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="eec4b-107">[![Planejamento](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="eec4b-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="eec4b-108">Planejamento</span><span class="sxs-lookup"><span data-stu-id="eec4b-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="eec4b-109">[![Preparar](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="eec4b-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="eec4b-110">Preparação</span><span class="sxs-lookup"><span data-stu-id="eec4b-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="eec4b-111">[![Simular ameaças](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="eec4b-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="eec4b-112">Simular ameaças</span><span class="sxs-lookup"><span data-stu-id="eec4b-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Fechar e resumir](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="eec4b-114">Fechar e resumir</span><span class="sxs-lookup"><span data-stu-id="eec4b-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="eec4b-115">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="eec4b-115">*You are here!*</span></span>|


<span data-ttu-id="eec4b-116">No momento, você está na fase de fechamento e resumo.</span><span class="sxs-lookup"><span data-stu-id="eec4b-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="eec4b-117">Você acabou de executar uma simulação de ataque avançada somente de memória que executou o código remotamente em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="eec4b-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="eec4b-118">Você viu como o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Identidade detectam e criam alertas sobre atividades mal-intencionadas furtivas.</span><span class="sxs-lookup"><span data-stu-id="eec4b-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="eec4b-119">Você também viu como alertas de fontes diferentes são entregues juntamente com outras informações contextuais em um único incidente no portal do Centro de Segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eec4b-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="eec4b-120">Experimentar essa integração permite que os analistas soc investiguem e tomem as medidas necessárias.</span><span class="sxs-lookup"><span data-stu-id="eec4b-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="eec4b-121">Você também criou uma consulta de busca avançada que identificará emails de entrada onde o usuário abriu ou salvou o anexo e criou a detecção com base nessa consulta.</span><span class="sxs-lookup"><span data-stu-id="eec4b-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="eec4b-122">Você chegou ao final do processo depois que todos os testes foram concluídos.</span><span class="sxs-lookup"><span data-stu-id="eec4b-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="eec4b-123">A saída final deve ser:</span><span class="sxs-lookup"><span data-stu-id="eec4b-123">The final output should be:</span></span>

- <span data-ttu-id="eec4b-124">Um scorecard concluído</span><span class="sxs-lookup"><span data-stu-id="eec4b-124">A completed scorecard</span></span>
- <span data-ttu-id="eec4b-125">Um relatório detalhado das descobertas do piloto</span><span class="sxs-lookup"><span data-stu-id="eec4b-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="eec4b-126">Uma decisão sobre como seguir em frente</span><span class="sxs-lookup"><span data-stu-id="eec4b-126">A decision on how to move forward</span></span>

<span data-ttu-id="eec4b-127">Apresente os relatórios de sua saída final para as partes [](./prepare-mtpeval.md) interessadas internas (que você identificou durante a fase de preparação) e contatos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eec4b-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-mtpeval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="eec4b-128">Esse esforço garante que qualquer comentário possa ser usado para melhorar produtos e documentação.</span><span class="sxs-lookup"><span data-stu-id="eec4b-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="eec4b-129">Esperamos que você tenha curtido essa simulação.</span><span class="sxs-lookup"><span data-stu-id="eec4b-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="eec4b-130">Comece a implementar o que você aprendeu em uma escala maior em sua organização para obter o máximo da solução de segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="eec4b-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="eec4b-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="eec4b-131">Next step</span></span>
<span data-ttu-id="eec4b-132">Saiba mais sobre os pilares do Microsoft 365 Defender por meio dos seguintes guias interativos:</span><span class="sxs-lookup"><span data-stu-id="eec4b-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="eec4b-133">Proteger sua organização com o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="eec4b-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="eec4b-134">Detecção de atividades suspeitas e possíveis ataques com o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="eec4b-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="eec4b-135">Detectar ameaças e gerenciar alertas com o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eec4b-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="eec4b-136">Investigar e remediar ameaças com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="eec4b-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)