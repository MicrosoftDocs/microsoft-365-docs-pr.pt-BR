---
title: Investigar incidentes no Microsoft Defender ATP
description: Consulte alertas associados, gerencie o incidente e consulte metadados de alerta para ajudá-lo a investigar um incidente
keywords: investigar, incidente, alertas, metadados, risco, fonte de detecção, dispositivos afetados, padrões, correlação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5a74da55d733d690cb218c78b87b67d6eba6b9d2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186048"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Investigar incidentes no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Investigue incidentes que afetam sua rede, entenda o que significam e cole evidências para resolvê-los. 

Ao investigar um incidente, você verá:
- Detalhes do incidente
- Comentários e ações de incidentes
- Guias (alertas, dispositivos, investigações, evidências, gráfico)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a>Analisar detalhes de incidentes 
Clique em um incidente para ver o **painel Incidente.** Selecione **Abrir página de incidentes** para ver os detalhes do incidente e informações relacionadas (alertas, dispositivos, investigações, evidências, gráfico). 

![Imagem dos detalhes do incidente1](images/atp-incident-details.png)

### <a name="alerts"></a>Alertas
Você pode investigar os alertas e ver como eles foram vinculados em um incidente. Os alertas são agrupados em incidentes com base nos seguintes motivos:
- Investigação automatizada - A investigação automatizada disparou o alerta vinculado ao investigar o alerta original 
- Características do arquivo - Os arquivos associados ao alerta têm características semelhantes
- Associação manual - Um usuário vinculado manualmente aos alertas
- Hora próxima - Os alertas foram disparados no mesmo dispositivo em um determinado período de tempo
- Mesmo arquivo - Os arquivos associados ao alerta são exatamente os mesmos
- Mesma URL - A URL que disparou o alerta é exatamente a mesma

![Imagem da guia alertas com a página detalhes do incidente mostrando os motivos pelos quais os alertas foram vinculados juntos nesse incidente](images/atp-incidents-alerts-reason.png)

Você também pode gerenciar um alerta e ver metadados de alerta junto com outras informações. Para obter mais informações, consulte [Investigar alertas](investigate-alerts.md). 

### <a name="devices"></a>Dispositivos
Você também pode investigar os dispositivos que fazem parte, ou relacionados a um determinado incidente. Para obter mais informações, consulte [Investigar dispositivos](investigate-machines.md).

![Guia Imagem dos dispositivos na página detalhes do incidente](images/atp-incident-device-tab.png)

### <a name="investigations"></a>Investigações
Selecione **Investigações** para ver todas as investigações automáticas lançadas pelo sistema em resposta aos alertas de incidentes.

![Guia Imagem de investigações na página detalhes do incidente](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>Passando pelas evidências
O Microsoft Defender para Ponto de Extremidade investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo a você autoresponse e informações sobre os arquivos importantes, processos, serviços e muito mais. 

Cada uma das entidades analisadas será marcada como infectado, remediado ou suspeito. 

![Guia Imagem da evidência na página detalhes do incidente](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>Visualizando ameaças de segurança cibernética associadas 
O Microsoft Defender for Endpoint agrega as informações de ameaça em um incidente para que você possa ver os padrões e as correlações provenientes de vários pontos de dados. Você pode exibir essa correlação por meio do gráfico de incidentes.

### <a name="incident-graph"></a>Gráfico de incidentes
O **Graph** conta a história do ataque de segurança cibernética. Por exemplo, ele mostra qual foi o ponto de entrada, qual indicador de comprometimento ou atividade foi observado em qual dispositivo. etc.

![Imagem do gráfico de incidentes](images/atp-incident-graph-tab.png)

Você pode clicar nos círculos no gráfico de incidentes para exibir os detalhes dos arquivos mal-intencionados, detecções de arquivo associados, quantas instâncias houveram em todo o mundo, se ela foi observada em sua organização, em caso afirmado, quantas instâncias.

![Imagem dos detalhes do incidente](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Fila de incidentes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Investigar incidentes no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Gerenciar o Microsoft Defender para incidentes de ponto de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
