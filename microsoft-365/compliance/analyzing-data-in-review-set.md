---
title: Analisar dados em um conjunto de revisão em Advanced eDiscovery
f1.keywords:
- NOCSH
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
description: Saiba mais sobre as ferramentas disponíveis para organizar conjuntos de documentos ao analisar um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751366"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analisar dados em um conjunto de revisão em Advanced eDiscovery

Quando o número de documentos coletados é grande, pode ser difícil revisá-los todos. Advanced eDiscovery fornece várias ferramentas para analisar os documentos para reduzir o volume de documentos a serem revisados sem qualquer perda de informações e para ajudá-lo a organizar os documentos de maneira coerente. Para saber mais sobre esses recursos, consulte:

- [Próximo detecção duplicada](near-duplicate-detection-in-advanced-ediscovery.md)

- [Threading de emails](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

Para analisar dados em um conjunto de revisão:

1. Configure as configurações de análise para seu caso. Para obter mais informações, consulte [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Abra o conjunto de revisão que você deseja analisar.

3. Clique **em Gerenciar conjunto de revisão**.

4. Clique **em Executar análise para o conjunto de revisão**.

Você pode verificar o andamento da análise na guia **Trabalhos** do caso.

 Depois que a análise for concluída, você poderá exibir o relatório de análise, executar consultas no conjunto de revisão nas saídas da análise (consulte [Consulta](review-set-search.md)no conjunto de revisão ) e ver documentos relacionados de um determinado documento (consulte [Reviewing data in review set](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Relatório de análise

Para exibir um relatório de análise para um conjunto de revisão:

1. Abra o conjunto de revisão.

2. Clique **em Gerenciar conjunto de revisão**.

3. Clique **em Exibir relatório**.

O relatório tem sete componentes da análise:

- **População de destino:** O número de mensagens de email, anexos e documentos soltos encontrados no conjunto de revisão.

- **Documentos (excluindo anexos):** O número de documentos soltos que são pivôs, duplicatas próximas exclusivas de um pivô ou uma duplicata exata de outro documento.

- **Emails:** O número de mensagens de email inclusivas, cópias inclusivas, menoss inclusivas ou nenhuma das anteriores.

- **Anexos:** O número de anexos de email que são exclusivos ou duplicados de outro anexo de email no conjunto de revisão.

- **Número de arquivos por tipo:** O número de arquivos, identificado por extensão de arquivo.

- **Documentos por fonte:** Um resumo do conteúdo por sua fonte de dados original.

- **Documentos agregados por processo:** Um resumo do conteúdo por processos de conjunto de revisão. 
