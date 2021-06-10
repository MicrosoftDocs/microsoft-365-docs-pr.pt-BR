---
title: Central de Segurança do Microsoft Defender Painel de operações de segurança
description: Use o painel para identificar dispositivos em risco, acompanhar o status do serviço e ver estatísticas e informações sobre dispositivos e alertas.
keywords: painel, alertas, novo, em andamento, resolvido, risco, dispositivos em risco, infecções, relatórios, estatísticas, gráficos, gráficos, saúde, detecções de malware ativo, categoria de ameaças, categorias, roubo de senha, ransomware, exploração, ameaça, baixa gravidade, malware ativo
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053573"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Central de Segurança do Microsoft Defender Painel de operações de segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

O **painel de operações de segurança** é onde os recursos detecção e resposta de ponto de extremidade são a superfície. Ele fornece uma visão geral de alto nível de onde as detecções foram vistas e realça onde as ações de resposta são necessárias. 

O painel exibe um instantâneo de:

- Alertas ativos
- Dispositivos em risco
- Saúde do sensor
- Integridade do serviço
- Relatórios diários de dispositivos
- Investigações automatizadas ativas
- Estatísticas de investigações automatizadas
- Usuários em risco
- Atividades suspeitas


![Painel de operações de segurança](images/atp-sec-ops-dashboard.png)

Você pode explorar e investigar alertas e dispositivos para determinar rapidamente se, onde e quando atividades suspeitas ocorreram em sua rede para ajudá-lo a entender o contexto em que eles surgiram.

No painel **Operações de segurança,** você verá eventos agregados para facilitar a identificação de eventos significativos ou comportamentos em um dispositivo. Você também pode detalhar eventos granulares e indicadores de baixo nível.

Ele também tem blocos clicáveis que dão dicas visuais sobre o estado de saúde geral da sua organização. Cada tile abre uma exibição detalhada da visão geral correspondente.

## <a name="active-alerts"></a>Alertas ativos
Você pode exibir o número geral de alertas ativos dos últimos 30 dias em sua rede a partir do azulejo. Os alertas são agrupados **em Novo** e **Em andamento.**

![Clique em cada fatia ou severidade para ver uma lista de alertas dos últimos 30 dias](images/active-alerts-tile.png)

Cada grupo é ainda mais sub categorizado em seus níveis de gravidade de alerta correspondentes. Clique no número de alertas dentro de cada anel de alerta para ver uma exibição classificação da fila dessa categoria (**Novo** **ou Em andamento**).

Para obter mais informações, consulte Visão [geral de alertas.](alerts-queue.md)

Cada linha inclui uma categoria de gravidade de alerta e uma breve descrição do alerta. Você pode clicar em um alerta para ver sua exibição detalhada. Para obter mais informações, [consulte Investigar o Microsoft Defender para alertas](investigate-alerts.md) de ponto de extremidade e visão geral de [alertas.](alerts-queue.md)


## <a name="devices-at-risk"></a>Dispositivos em risco
Esse azulejo mostra uma lista de dispositivos com o maior número de alertas ativos. O número total de alertas para cada dispositivo é mostrado em um círculo ao lado do nome do dispositivo e, em seguida, categorizado ainda mais por níveis de severidade no final do azulejo (passe o mouse sobre cada barra de gravidade para ver seu rótulo).

![O telha dispositivos em risco mostra uma lista de dispositivos com o maior número de alertas e uma divisão da gravidade dos alertas](images/devices-at-risk-tile.png)

Clique no nome do dispositivo para ver detalhes sobre esse dispositivo. Para obter mais informações, [consulte Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).

Você também pode clicar na lista **Dispositivos** na parte superior do azulejo para ir diretamente para a lista **Dispositivos**, classificação pelo número de alertas ativos. Para obter mais informações, [consulte Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).

## <a name="devices-with-sensor-issues"></a>Dispositivos com problemas de sensor
O **pacote Dispositivos com problemas** de sensor fornece informações sobre a capacidade do dispositivo individual de fornecer dados do sensor ao serviço Microsoft Defender para Ponto de Extremidade. Ele relata quantos dispositivos exigem atenção e ajuda a identificar dispositivos problemáticos.

![Dispositivos com problemas de sensor de tile](images/atp-tile-sensor-health.png)

Há dois indicadores de status que fornecem informações sobre o número de dispositivos que não estão relatando corretamente para o serviço:
- **Mal configurado** – esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço do Microsoft Defender para Ponto de Extremidade e podem ter erros de configuração que precisam ser corrigidos.
- **Inativos** - Dispositivos que pararam de relatar para o serviço Microsoft Defender para Ponto de Extremidade por mais de sete dias no mês passado.

Quando você clicar em qualquer um dos grupos, você será direcionado para a lista de dispositivos, filtrado de acordo com sua escolha. Para obter mais informações, consulte [Verificar o estado do sensor](check-sensor-status.md) e investigar [dispositivos](investigate-machines.md).

## <a name="service-health"></a>Integridade do serviço
O **azulejo de** saúde do serviço informa se o serviço está ativo ou se há problemas.

![O azulejo de saúde do serviço mostra um indicador geral do serviço](images/status-tile.png)

Para obter mais informações sobre a saúde do serviço, consulte [Check the Microsoft Defender for Endpoint service health](service-status.md).


## <a name="daily-devices-reporting"></a>Relatórios diários de dispositivos
O **gráfico de relatório** de dispositivos diários mostra um gráfico de barras que representa o número de dispositivos que relatam diariamente nos últimos 30 dias. Passe o mouse sobre barras individuais no gráfico para ver o número exato de dispositivos relatando em cada dia.

![Imagem do tile de relatório de dispositivos diários](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a>Investigações automatizadas ativas
Você pode exibir o número geral de investigações automatizadas dos últimos 30 dias em sua rede a partir do conjunto de **investigações automatizadas** ativas. As investigações são agrupadas em **Ação Pendente,** **Aguardando dispositivo** e **Execução.**

![Inmage of active automated investigations](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a>Estatísticas de investigações automatizadas
Este tile mostra estatísticas relacionadas a investigações automatizadas nos últimos sete dias. Ele mostra o número de investigações concluídas, o número de investigações remediadas com êxito, o tempo médio de espera necessário para que uma investigação seja iniciada, o tempo médio necessário para correção de um alerta, o número de alertas investigados e o número de horas de automação salvas de uma investigação manual típica. 

![Imagem das estatísticas de investigações automatizadas](images/atp-automated-investigations-statistics.png)

Você pode clicar em **Investigações Automatizadas,** **Investigações** Corretivas e **Alertas investigados** para navegar até a página **Investigações,** filtrada pela categoria apropriada. Isso permite que você veja uma divisão detalhada das investigações no contexto.

## <a name="users-at-risk"></a>Usuários em risco
O azulejo mostra uma lista de contas de usuário com alertas mais ativos e o número de alertas vistos em alertas altos, médios ou baixos. 

![As contas de usuário em um tile de risco mostram uma lista de contas de usuário com o maior número de alertas e uma divisão da gravidade dos alertas](images/atp-users-at-risk.png)

Clique na conta de usuário para ver detalhes sobre a conta de usuário. Para obter mais informações, [consulte Investigar uma conta de usuário](investigate-user.md).

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>Tópicos relacionados
- [Entender o portal do Microsoft Defender para Ponto de Extremidade](use.md)
- [Visão geral do portal](portal-overview.md)
- [Exibir o painel gerenciamento de & de vulnerabilidades](tvm-dashboard-insights.md)
- [Exibir o painel de análise de ameaças e tomar ações de mitigação recomendadas](threat-analytics.md)
