---
title: Incidentes no Microsoft 365 Defender
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861618"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).
>

Um incidente no Microsoft 365 Defender é uma coleção de alertas correlacionados e dados associados que comentam a história de um ataque. 

Os serviços e aplicativos do Microsoft 365 criam alertas quando detectam um evento ou atividade suspeito ou mal-intencionado. Alertas individuais fornecem dicas valiosas sobre um ataque concluído ou contínuo. No entanto, os ataques geralmente empregam várias técnicas contra diferentes tipos de entidades, como dispositivos, usuários e caixas de correio. O resultado são vários alertas para várias entidades em seu locatário. 

Como reunir os alertas individuais para obter informações sobre um ataque pode ser desafiador e demorado, o Microsoft 365 Defender agrega automaticamente os alertas e suas informações associadas a um incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Como o Microsoft 365 Defender correlaciona eventos de entidades em um incidente":::

Assista a esta breve visão geral dos incidentes no Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Agrupar alertas relacionados a um incidente oferece uma visão abrangente de um ataque. Por exemplo, você pode ver:

- Onde o ataque começou.
- Quais táticas foram usadas.
- Até que ponto o ataque foi para o seu locatário.
- O escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados. 
- Todos os dados associados ao ataque.

Se [habilitado, o](m365d-enable.md)Microsoft 365 Defender pode investigar e resolver alertas automaticamente por meio da automação e da inteligência artificial. Você também pode executar etapas de correção adicionais para resolver o ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidentes e alertas no centro de segurança do Microsoft 365

Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="A página Incidentes no centro de segurança do Microsoft 365":::

Selecionar um nome de incidente exibe um resumo do incidente e fornece acesso a guias com informações adicionais.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro de segurança do Microsoft 365":::

As guias adicionais para um incidente são:

- Alertas 

  Todos os alertas relacionados ao incidente e suas informações.

- Dispositivos

  Todos os dispositivos que foram identificados para fazer parte ou relacionados ao incidente.

- Usuários

  Todos os usuários identificados para fazer parte ou relacionados ao incidente.

- Caixas de correio

  Todas as caixas de correio identificadas para fazer parte ou relacionadas ao incidente.

- Investigações

  Todas as investigações automatizadas disparadas por alertas no incidente.

- Evidências e resposta

  Todos os eventos com suporte e entidades suspeitas nos alertas no incidente.

Aqui está a relação entre um incidente e seus dados e as guias de um incidente no centro de segurança do Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="A relação de um incidente e seus dados com as guias de um incidente no centro de segurança do Microsoft 365":::

## <a name="next-step"></a>Próxima etapa

A fila de **incidentes da página Incidentes** lista os incidentes mais recentes. A partir daqui, você pode:

- Confira quais incidentes devem ser [priorizados](incident-queue.md) com base na gravidade e em outros fatores. 
- Execute uma [investigação](investigate-incidents.md) de um incidente.
- [Gerencie incidentes](manage-incidents.md), que inclui renomeação, atribuição, classificação e adição de marcas para o fluxo de trabalho de gerenciamento de incidentes.
