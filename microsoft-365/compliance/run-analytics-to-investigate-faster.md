---
title: Executar análise para investigar mais rápido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073170"
---
# <a name="run-analytics-to-investigate-faster"></a>Executar análise para investigar mais rápido

Quando uma coleção de evidências é grande, pode ser difícil revisar todas elas. Um conjunto de evidências geralmente inclui várias cópias das mesmas ou de documentos ou mensagens de email semelhantes. As investigações de dados (visualização) fornecem várias ferramentas de análise que podem ajudá-lo a reduzir o volume de documentos que precisam ser revisados sem qualquer perda de informações. Para saber mais sobre esses recursos, confira:

- [Detecção de duplicata próxima](near-duplicates.md)

- [Conversa de email](email-threading.md)

- [Temas](themes.md)

Para analisar dados em um conjunto de evidências:

1. Configure as definições de análise para sua investigação. Para obter mais informações, consulte [Configurar definições de pesquisa e análise](configure-search-analytics-settings.md).

2. Abra o conjunto de evidência.

3. Clique em **gerenciar evidência**.

4. Em **análise**, clique em **analisar**.

Você pode verificar o andamento da análise na guia **trabalhos** em sua investigação. O tipo de trabalho disparado é chamado de **análise de execução**.

 Após a conclusão da análise, você pode ver uma lista de duplicatas exatas ou quase duplicatas do documento que está sendo revisado localizado no painel à direita. Para selecionar todas as duplicatas do documento que você está exibindo, você pode facilmente fazer isso usando este painel. Para saber mais sobre outros recursos neste painel, consulte [Review data in Evidence](review-data-in-evidence.md). 

Você também pode executar consultas adicionais dentro de suas evidências usando as saídas da análise, como temas. Para obter mais informações, consulte [Query The data in Evidence](evidence-query.md).

## <a name="analytics-report"></a>Relatório de análise

Para exibir um relatório de análise de suas evidências:

1. Abra o conjunto de evidência.

2. Clique em **gerenciar evidência**.

3. Em **análise**, clique em **Exibir relatório**.

O relatório tem quatro componentes da análise:

- **Divisão** -o número de emails, anexos e documentos brutos encontrados no conjunto de evidências.

- **Emails** : o número de mensagens do eamil incluindo, inclusive minuses, cópias inclusivas ou nenhuma das opções acima.
   - Inclusive: a última mensagem no thread de email que contém todo o histórico anterior e requer revisão.
   - Minuses inclusivo: a mensagem no thread que contém um ou mais anexos diferentes que requer revisão.
   - Cópias inclusivas: a mensagem é uma cópia de outra mensagem inclusiva ou inclusiva (assunto e corpo).

- **Attachments** : o número de anexos de email exclusivos ou duplicados de um anexo de email diferente dentro da mesma evidência.

- **Documentos (exceto anexos de email)** : o número de documentos exclusivos que exigem revisão, por exemplo, o documento mais representativo do conjunto quase duplicado ou uma duplicata exata de outro documento.