---
title: Revisar alertas no Microsoft Defender para Ponto de Extremidade
description: Revise as informações de alerta, incluindo um artigo de alerta visualizado e detalhes para cada etapa da cadeia.
keywords: incidentes, incidentes, máquinas, dispositivos, usuários, alertas, alertas, investigação, gráfico, evidência
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844017"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Revisar alertas no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

A página de alerta no Microsoft Defender para Ponto de Extremidade fornece contexto completo ao alerta, combinando sinais de ataque e alertas relacionados ao alerta selecionado, para construir um histórico de alerta detalhado.

Triagem rápida, investigação e tomar medidas eficazes em alertas que afetam sua organização. Entenda por que eles foram disparados e seu impacto de um local. Saiba mais nesta visão geral.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>Como começar com um alerta

Selecionar o nome de um alerta no Defender para Ponto de Extremidade o fará parar em sua página de alerta. Na página de alerta, todas as informações serão mostradas no contexto do alerta selecionado. Cada página de alerta consiste em 4 seções:

1. **O título do alerta** mostra o nome do alerta e está lá para lembrar qual alerta iniciou sua investigação atual, independentemente do que você selecionou na página.
2. [**Os ativos**](#review-affected-assets) afetados listam cartões de dispositivos e usuários afetados por esse alerta que podem ser clicados para obter mais informações e ações.
3. O **artigo de alerta** exibe todas as entidades relacionadas ao alerta, interconectadas por uma exibição em árvore. O alerta no título será aquele em foco quando você chegar pela primeira vez na página do alerta selecionado. As entidades no histórico de alerta são expansíveis e clicáveis, para fornecer informações adicionais e acelerar a resposta, permitindo que você tome ações diretamente no contexto da página de alerta. Use o artigo de alerta para iniciar sua investigação. Saiba como em [Investigar alertas no Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/investigate-alerts).
4. O **painel de detalhes** mostrará os detalhes do alerta selecionado no início, com detalhes e ações relacionadas a esse alerta. Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alertas, o painel de detalhes mudará para fornecer informações contextuais e ações para o objeto selecionado.

Observe o status de detecção do alerta. 
- Impedido – A tentativa de ação suspeita foi evitada. Por exemplo, um arquivo não foi gravado em disco ou executado.
![Uma página de alerta mostrando ameaça foi impedida](images/detstat-prevented.png)
- Bloqueado – Comportamento suspeito foi executado e bloqueado. Por exemplo, um processo foi executado, mas como ele exibiu comportamentos suspeitos posteriormente, o processo foi encerrado.
![Uma página de alerta mostrando ameaça foi bloqueada](images/detstat-blocked.png)
- Detectado – um ataque foi detectado e possivelmente ainda está ativo.
![Uma página de alerta mostrando ameaça foi detectada](images/detstat-detected.png)




Em seguida, você  também pode revisar os detalhes de investigação automatizados no painel de detalhes do seu alerta, para ver quais ações já foram tomadas, bem como ler a descrição do alerta para ações recomendadas.

![Um trecho do painel de detalhes com a descrição do alerta e as seções de investigação automática realçadas](images/alert-air-and-alert-description.png)

Outras informações disponíveis no painel de detalhes quando o alerta é aberto incluem técnicas MITRE, origem e detalhes contextuais adicionais.




## <a name="review-affected-assets"></a>Revisar ativos afetados

Selecionar um dispositivo ou um cartão de usuário nas seções de ativos afetados alterna para os detalhes do dispositivo ou do usuário no painel de detalhes.

- **Para dispositivos,** o painel de detalhes exibirá informações sobre o próprio dispositivo, como Domínio, Sistema Operacional e IP. Alertas ativos e os usuários conectados nesse dispositivo também estão disponíveis. Você pode executar uma ação imediata isolando o dispositivo, restringindo a execução do aplicativo ou executando uma verificação antivírus. Como alternativa, você pode coletar um pacote de investigação, iniciar uma investigação automatizada ou ir até a página do dispositivo para investigar do ponto de vista do dispositivo.

   ![Um trecho do painel de detalhes quando um dispositivo é selecionado](images/device-page-details.png)

- Para **usuários,** o painel de detalhes exibirá informações detalhadas do usuário, como o nome SAM e SID do usuário, bem como os tipos de logon executados por esse usuário e quaisquer alertas e incidentes relacionados a ele. Você pode selecionar *Abrir página do usuário* para continuar a investigação do ponto de vista desse usuário.

   ![Um trecho do painel de detalhes quando um usuário é selecionado](images/user-page-details.png)


## <a name="related-topics"></a>Tópicos relacionados

- [Exibir e organizar a fila de incidentes](view-incidents-queue.md)
- [Investigar incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
