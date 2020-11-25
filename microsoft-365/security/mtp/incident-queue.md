---
title: Priorizar incidentes no Microsoft 365 defender
description: Saiba como filtrar incidentes da fila de incidentes no Microsoft 365 defender
keywords: incidente, fila, visão geral, dispositivos, identidades, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409250"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes no Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



O Microsoft 365 defender aplica a análise de correlação e agrega todos os alertas e investigações relacionados de produtos diferentes em um único incidente. O Microsoft 365 defender também dispara alertas exclusivos em atividades que só podem ser identificados como mal-intencionados, dada a visibilidade de ponta a ponta que a Microsoft 365 defender tem em toda a imobiliária e pacote de produtos. Este modo de exibição fornece ao analista de operações de segurança a história de ataque mais ampla, o que ajuda a entender melhor e lidar com ameaças complexas em toda a organização.


A **Fila de incidentes** exibe um conjunto de incidentes sinalizados de vários dispositivos, usuários e caixas de correio. Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.


![Imagem da fila de incidentes](../../media/incidents-queue.png) 

Por padrão, a fila na central de segurança do Microsoft 365 exibe incidentes vistos nos últimos 30 dias. O incidente mais recente fica na parte superior da lista para que você possa vê-lo primeiro.

A fila de incidentes expõe colunas personalizáveis que lhe dão visibilidade de diferentes características do incidente ou das entidades contidas. Isso ajuda você a tomar decisões informadas sobre a priorização de incidentes para lidar.

Para obter visibilidade adicional em um relance, o nome automático de incidentes gera nomes de incidentes com base em atributos de alerta como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente.

Por exemplo: *incidente de vários estágios em vários pontos de extremidade relatados por várias fontes.*

> [!NOTE]
> Incidentes que existiam antes da distribuição da nomeação automática de incidentes não terão o nome alterado.

A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você realize uma ampla varredura de todos os incidentes existentes no seu ambiente ou decida se concentrar em um cenário ou ameaça específico. A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata. 

## <a name="available-filters"></a>Filtros disponíveis

### <a name="assigned-to"></a>Atribuído a
Você pode optar por mostrar alertas que são atribuídos a você ou aqueles tratados pela automação.

### <a name="categories"></a>Categorias
Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos. 

### <a name="classification"></a>Classificação
Filtrar incidentes com base nas classificações de conjunto dos alertas relacionados. Os valores incluem alertas verdadeiros, falsos alertas ou não definidos.

### <a name="data-sensitivity"></a>Confidencialidade de dados
Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos. Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.

>[!NOTE]
>Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.

### <a name="device-group"></a>Grupo de dispositivos
Filtrar por grupos de dispositivos definidos.

### <a name="investigation-state"></a>Estado de investigação
Filtrar incidentes pelo status de investigação automatizada. 

### <a name="multiple-categories"></a>Várias categorias 
Você pode optar por ver apenas os incidentes que foram mapeados para várias categorias e podem possivelmente causar mais danos. 

### <a name="multiple-service-sources"></a>Várias fontes de serviço 
Filtro para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft defender para ponto de extremidade, Microsoft Cloud app Security, Microsoft defender para identidade, Microsoft defender para Office 365).

### <a name="os-platform"></a>Plataforma do sistema operacional
Limitar o modo de exibição fila de incidentes por sistema operacional.

### <a name="service-sources"></a>Fontes de serviço
Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida. 

### <a name="severity"></a>Severity
A gravidade de um incidente indica o impacto que ele pode ter em seus ativos. Quanto maior a gravidade, maior o impacto e normalmente requer a atenção mais imediata. 

### <a name="status"></a>Status
Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.




## <a name="next-steps"></a>Próximas etapas
Após determinar qual incidente requer a prioridade mais alta, você pode continuar a fazer um trabalho mais investigativo em um incidente.
- [Investigar incidentes](investigate-incidents.md)


## <a name="see-also"></a>Confira também
- [Visão geral dos incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
