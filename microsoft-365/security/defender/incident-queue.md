---
title: Priorizar incidentes no Microsoft 365 Defender
description: Saiba como filtrar incidentes da fila de incidentes no Microsoft 365 Defender
keywords: incidente, fila, visão geral, dispositivos, identidades, usuários, caixa de correio, email, incidentes
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
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887252"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

O Microsoft 365 Defender aplica análises de correlação e agrega alertas relacionados e investigações automatizadas de diferentes produtos em um incidente. O Microsoft 365 Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o pacote de produtos. Essa exibição fornece aos seus analistas de segurança uma história de ataque mais ampla, que os ajuda a entender melhor e lidar com ameaças complexas em toda a sua organização.

A **fila de incidentes** mostra uma coleção de incidentes que foram criados em dispositivos, usuários e caixas de correio. Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada. 

Você pode chegar à fila de incidentes de **Incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

Por padrão, a fila de incidentes no centro de segurança do Microsoft 365 exibe incidentes vistos nos últimos seis meses. O incidente mais recente está na parte superior da lista para que você possa vê-lo primeiro.

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

## <a name="incident-response-workflow"></a>Fluxo de trabalho de resposta a incidentes

Este é o fluxo de trabalho típico para responder a incidentes:

1. Identificar e triagem dos incidentes de maior prioridade para investigação e resolução.
2. Para cada incidente de alta prioridade, inicie uma [investigação:](investigate-incidents.md)

   a. Exibir o resumo do incidente para entender seu escopo e gravidade e quais entidades são afetadas (a **guia Resumo).**

   b. Comece a olhar para os alertas para entender sua origem, escopo e gravidade (a **guia Alertas).**

   c. Conforme necessário, reúna informações sobre dispositivos, usuários e caixas de correio afetados (as guias **Dispositivos,** **Usuários** e **Caixas** de Correio).

   d. Veja como o Microsoft 365 Defender resolveu automaticamente alguns alertas (a guia **Investigações).**
   
   e. Conforme necessário, use informações no conjunto de dados do incidente para obter mais informações (a **guia Evidências e Resposta).**

   À medida que você investiga, você deve se preocupar com:

   - Contenção: reduzindo qualquer impacto adicional em seu locatário.
   - Erradicação: Removendo a ameaça de segurança.
   - Recuperação: restaurando os recursos do locatário para o estado em que estavam antes do incidente.

3. Depois de resolver o incidente, aproveite o tempo para:

   - Entenda o tipo de ataque e seu impacto.
   - Pesquise o ataque na comunidade de segurança para uma tendência de ataque de segurança.
   - Lembre-se do fluxo de trabalho usado para resolver o incidente e atualizar seus fluxos de trabalho padrão e playbooks conforme necessário.
   - Determine se as alterações na postura de segurança são necessárias e tome as etapas para implementá-las.

Aqui está um resumo do processo básico.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="O processo básico para investigar incidentes":::

## <a name="next-step"></a>Próxima etapa

Depois de determinar qual incidente requer a maior prioridade, selecione-o e inicie a [investigação.](investigate-incidents.md)

## <a name="see-also"></a>Confira também
- [Visão geral dos incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
