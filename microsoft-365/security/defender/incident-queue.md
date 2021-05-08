---
title: Priorizar incidentes no Microsoft 365 Defender
description: Saiba como filtrar incidentes da fila de incidentes no Microsoft 365 Defender
keywords: incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response
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
ms.openlocfilehash: 47d066fa20abe963f7afaa3b88cecc96fa6e87fc
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259575"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Microsoft 365 O Defender aplica análises de correlação e agrega alertas relacionados e investigações automatizadas de diferentes produtos em um incidente. Microsoft 365 O Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o pacote de produtos. Essa exibição fornece aos seus analistas de segurança uma história de ataque mais ampla, que os ajuda a entender melhor e lidar com ameaças complexas em toda a sua organização.

A **fila de incidentes** mostra uma coleção de incidentes que foram criados em dispositivos, usuários e caixas de correio. Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada. 

Você pode chegar à fila de incidentes & alertas > **Incidentes** no início rápido do centro de segurança Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com) Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

A **seção Incidentes e alertas** mais recentes mostra um gráfico do número de alertas recebidos e incidentes criados nas últimas 24 horas.

Por padrão, a fila de incidentes no centro de segurança Microsoft 365 exibe incidentes vistos nos últimos seis meses. O incidente mais recente está na parte superior da lista para que você possa vê-lo primeiro.

A fila de incidentes tem colunas personalizáveis (selecione **Escolher colunas**) que dão visibilidade a diferentes características do incidente ou das entidades impactadas. Isso ajuda você a tomar uma decisão informada sobre a priorização de incidentes para análise.

Para obter visibilidade adicional rapidamente, a nomenização automática de incidentes gera nomes de incidentes com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente.

Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*

> [!NOTE]
> Incidentes que existiam antes da adoção da nomenização automática de incidentes não terão seu nome alterado.

A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você execute uma ampla varredura de todos os incidentes existentes em seu ambiente ou decida se concentrar em um cenário ou ameaça específico. A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata. 

## <a name="available-filters"></a>Filtros disponíveis

Na fila de incidentes padrão, você pode selecionar **Filtros** para ver um painel Filtros, do qual você pode exibir um conjunto filtrado de incidentes. Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exemplo do painel filtros para a fila de incidentes":::

Esta tabela lista os nomes de filtro disponíveis.

| Nome do filtro | Descrição |
|:-------|:-----|
| Atribuído a | Você pode optar por mostrar alertas atribuídos a você ou aos manipulados pela automação. |
| Categorias | Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos. |
| Classificação | Filtrar incidentes com base nas classificações definidas dos alertas relacionados. Os valores incluem alertas verdadeiros, alertas falsos ou não definidos. |
| Confidencialidade de dados | Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos. Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes. <br><br> Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.|
| Grupo de dispositivos | Filtrar por grupos de dispositivos definidos. |
| Estado da investigação | Filtrar incidentes pelo status da investigação automatizada.  |
| Várias categorias | Você pode optar por ver apenas incidentes mapeados para várias categorias e, portanto, pode causar mais danos. |
| Várias fontes de serviço  | Filtrar para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender para Identidade, Microsoft Defender para Office 365). |
| Plataforma do sistema operacional | Limite a exibição de fila de incidentes pelo sistema operacional. |
| Fontes de serviço | Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida. |
| Severity | A gravidade de um incidente indica o impacto que ele pode ter em seus ativos. Quanto maior a gravidade, maior o impacto e normalmente exige a atenção mais imediata. |
| Status | Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos. |
|||

## <a name="next-step"></a>Próxima etapa

Depois de determinar qual incidente requer a maior prioridade, selecione-o e inicie a [análise.](investigate-incidents.md)

## <a name="see-also"></a>Confira também
- [Visão geral dos incidentes](incidents-overview.md)
- [Analisar os incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
