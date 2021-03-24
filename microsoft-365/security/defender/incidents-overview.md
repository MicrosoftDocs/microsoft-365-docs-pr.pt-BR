---
title: Visão geral de incidentes no Microsoft 365 Defender
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052531"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Visão geral de incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou executar seu projeto piloto em [produção](m365d-pilot.md?ocid=cx-evalpilot).
>


Os incidentes se baseiam em alertas relacionados. Os alertas são criados quando um evento ou uma atividade mal-intencionados são vistos na sua rede. Alertas individuais fornecem dicas valiosas sobre um ataque em tempo útil. No entanto, os ataques geralmente empregam vários vetores e técnicas para executar uma violação. Reunir pistas individuais pode ser desafiador e demorado.

Este vídeo curto fornece uma visão geral dos incidentes no Microsoft 365 Defender.
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Um incidente é uma coleção de alertas correlacionados que comentam a história de um ataque. Eventos mal-intencionados e suspeitos encontrados em diferentes entidades de dispositivo, usuário e caixa de correio na rede são agregados automaticamente pelo Microsoft 365 Defender. Agrupar alertas relacionados a um incidente proporciona aos defensores de segurança uma visão abrangente de um ataque. 

Por exemplo, os defensores de segurança podem ver onde o ataque começou, quais táticas foram usadas e até onde o ataque foi para a rede. Eles também podem ver o escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados, a gravidade do impacto e outros detalhes sobre entidades afetadas.

Se habilitado, o Microsoft 365 Defender pode investigar e resolver automaticamente os alertas individuais por meio de automação e inteligência artificial. Os defensores de segurança também podem executar etapas de correção adicionais para resolver o ataque diretamente do ponto de vista de incidentes. 

Incidentes dos últimos 30 dias são mostrados na fila de incidentes. A partir daqui, os defensores de segurança podem ver quais incidentes devem ser priorizados com base no nível de risco e em outros fatores. 

Os defensores de segurança também podem renomear incidentes, atribuí-los a analistas individuais, classificar e adicionar marcas a incidentes para uma experiência de gerenciamento de incidentes melhor e mais personalizada.



## <a name="see-also"></a>Confira também
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)