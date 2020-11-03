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
ms.openlocfilehash: 1617e7b68346673785c72e90e6f5e94193d96488
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843013"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="ec09d-104">Fechar e resumir seu piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="ec09d-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec09d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ec09d-105">**Applies to:**</span></span>
- <span data-ttu-id="ec09d-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="ec09d-106">Microsoft 365 Defender</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Planejar seu projeto piloto do Microsoft 365 defender" />
      <br/><span data-ttu-id="ec09d-108">Planta </a></span><span class="sxs-lookup"><span data-stu-id="ec09d-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto" />
      <br/><span data-ttu-id="ec09d-110">Preparar </a></span><span class="sxs-lookup"><span data-stu-id="ec09d-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Executar as simulações de ataque do Microsoft 365 defender" />
      <br/><span data-ttu-id="ec09d-112">Simular ataque </a></span><span class="sxs-lookup"><span data-stu-id="ec09d-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Feche e resuma seu piloto do Microsoft 365 defender" />
      <br/><span data-ttu-id="ec09d-114">Fechar e resumir </a></span><span class="sxs-lookup"><span data-stu-id="ec09d-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="ec09d-115">Você está atualmente na fase de fechamento e resumo.</span><span class="sxs-lookup"><span data-stu-id="ec09d-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="ec09d-116">Você acabou de executar uma simulação avançada de ataque somente de memória que executou o código remotamente em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ec09d-116">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="ec09d-117">Você viu como o Microsoft defender for Endpoint e o Microsoft defender para identidade detectam e criam alertas sobre atividades mal-intencionadas fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="ec09d-117">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="ec09d-118">Você também viu como os alertas de fontes diferentes são entregues junto com outras informações contextuais em um único incidente no portal da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec09d-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="ec09d-119">A integração desse tipo permite que analistas do SOC investiguem e tomem a ação necessária.</span><span class="sxs-lookup"><span data-stu-id="ec09d-119">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="ec09d-120">Você também criou uma consulta de busca avançada que identificará emails de entrada onde o usuário abriu ou salvou o anexo e criou a detecção com base nessa consulta.</span><span class="sxs-lookup"><span data-stu-id="ec09d-120">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="ec09d-121">Você atingiu o final do processo após todos os testes terem concluído.</span><span class="sxs-lookup"><span data-stu-id="ec09d-121">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="ec09d-122">A saída final deve ser:</span><span class="sxs-lookup"><span data-stu-id="ec09d-122">The final output should be:</span></span>

- <span data-ttu-id="ec09d-123">Um scorecard concluído</span><span class="sxs-lookup"><span data-stu-id="ec09d-123">A completed scorecard</span></span>
- <span data-ttu-id="ec09d-124">Um relatório detalhado das conclusões do piloto</span><span class="sxs-lookup"><span data-stu-id="ec09d-124">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="ec09d-125">Uma decisão sobre como mover para frente</span><span class="sxs-lookup"><span data-stu-id="ec09d-125">A decision on how to move forward</span></span>

<span data-ttu-id="ec09d-126">Apresente os relatórios de sua saída final para os participantes internos (identificados durante a fase de [preparação](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) e contatos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec09d-126">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="ec09d-127">Tal esforço garante que qualquer feedback possa ser usado para melhorar os produtos e a documentação.</span><span class="sxs-lookup"><span data-stu-id="ec09d-127">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="ec09d-128">Esperamos que você tenha aproveitado essa simulação.</span><span class="sxs-lookup"><span data-stu-id="ec09d-128">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="ec09d-129">Comece a implementar o que você aprendeu em uma escala maior em sua organização para aproveitar ao máximo a solução de segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="ec09d-129">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec09d-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ec09d-130">Next step</span></span>
<span data-ttu-id="ec09d-131">Saiba mais sobre os pilares do Microsoft 365 defender por meio dos seguintes guias interativos:</span><span class="sxs-lookup"><span data-stu-id="ec09d-131">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="ec09d-132">Proteger sua organização com o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ec09d-132">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="ec09d-133">Detecção de atividades suspeitas e possíveis ataques com o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="ec09d-133">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="ec09d-134">Detectar ameaças e gerenciar alertas com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="ec09d-134">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="ec09d-135">Investigue e corrija ameaças com o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="ec09d-135">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
