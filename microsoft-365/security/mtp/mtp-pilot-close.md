---
title: Resumindo seus resultados do projeto de proteção contra ameaças da Microsoft
description: Conclua seu projeto piloto de proteção contra ameaças da Microsoft preenchendo o Scorecard, analisando suas descobertas de relatórios e decidindo como mover para frente.
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: ec8e630c3669b3eb7af8cb012a0ca361f8c77f1e
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368008"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="6af10-104">Fechar e resumir seu piloto de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6af10-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6af10-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6af10-105">**Applies to:**</span></span>
- <span data-ttu-id="6af10-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6af10-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Planejar seu projeto piloto de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="6af10-108">Planta </a></span><span class="sxs-lookup"><span data-stu-id="6af10-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/><span data-ttu-id="6af10-110">Preparar </a></span><span class="sxs-lookup"><span data-stu-id="6af10-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Executar as simulações de ataque de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="6af10-112">Simular ataque </a></span><span class="sxs-lookup"><span data-stu-id="6af10-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Feche e resuma seu piloto de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="6af10-114">Fechar e resumir </a></span><span class="sxs-lookup"><span data-stu-id="6af10-114">Close and summarize </a></span></span><br>
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

<span data-ttu-id="6af10-115">Você está atualmente na fase de fechamento e resumo.</span><span class="sxs-lookup"><span data-stu-id="6af10-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="6af10-116">Você acabou de simular um ataque avançado de memória que executou o código remotamente em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="6af10-116">You’ve just simulated an advanced memory-only attack that executed code remotely on a domain controller.</span></span> <span data-ttu-id="6af10-117">Você viu como o Microsoft defender ATP e o Azure ATP detectam e alertam sobre atividades mal-intencionadas fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="6af10-117">You’ve seen how Microsoft Defender ATP and Azure ATP detects and alerts on stealthy malicious activity.</span></span> <span data-ttu-id="6af10-118">Você também viu como os alertas de fontes diferentes são entregues junto com outras informações contextuais em um único incidente no portal da central de segurança do Microsoft 365, permitindo que os analistas do SOC investiguem e tomem a ação necessária.</span><span class="sxs-lookup"><span data-stu-id="6af10-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal, enabling SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="6af10-119">Você também criou uma consulta de busca avançada que identificará emails de entrada onde o usuário abriu ou salvou o anexo e criou a detecção com base nessa consulta.</span><span class="sxs-lookup"><span data-stu-id="6af10-119">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="6af10-120">Você atingiu o final do processo após todos os testes terem concluído.</span><span class="sxs-lookup"><span data-stu-id="6af10-120">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="6af10-121">A saída final deve ser:</span><span class="sxs-lookup"><span data-stu-id="6af10-121">The final output should be:</span></span>

- <span data-ttu-id="6af10-122">Um scorecard concluído</span><span class="sxs-lookup"><span data-stu-id="6af10-122">A completed scorecard</span></span>
- <span data-ttu-id="6af10-123">Um relatório detalhado das conclusões do piloto</span><span class="sxs-lookup"><span data-stu-id="6af10-123">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="6af10-124">Uma decisão sobre como mover para frente</span><span class="sxs-lookup"><span data-stu-id="6af10-124">A decision on how to move forward</span></span>

<span data-ttu-id="6af10-125">Essas informações devem ser apresentadas para os participantes internos (identificados durante a fase de [preparação](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) e contatos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6af10-125">This information should be presented to both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="6af10-126">Isso garante que qualquer feedback possa ser usado para melhorar os produtos e a documentação.</span><span class="sxs-lookup"><span data-stu-id="6af10-126">This ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="6af10-127">Esperamos que você tenha gostado dessa simulação e recomendamos começar a implementar o que você aprendeu.</span><span class="sxs-lookup"><span data-stu-id="6af10-127">We hope you enjoyed this simulation and are encouraged to start implementing what you've learned.</span></span>

## <a name="next-step"></a><span data-ttu-id="6af10-128">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6af10-128">Next step</span></span>
<span data-ttu-id="6af10-129">Saiba mais sobre os pilares de proteção contra ameaças da Microsoft por meio dos seguintes guias interativos:</span><span class="sxs-lookup"><span data-stu-id="6af10-129">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="6af10-130">Proteger sua organização com o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6af10-130">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="6af10-131">Detectar atividades suspeitas e possíveis ataques com o Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="6af10-131">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="6af10-132">Detectar ameaças e gerenciar alertas com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="6af10-132">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="6af10-133">Investigue e corrija ameaças com o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="6af10-133">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
