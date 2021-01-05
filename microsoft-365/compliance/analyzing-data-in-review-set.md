---
title: Analisar dados em um conjunto de revisão na descoberta eletrônica avançada
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
description: Saiba mais sobre as ferramentas disponíveis para organizar conjuntos de documentos ao analisar uma ocorrência de descoberta eletrônica avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751366"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analisar dados em um conjunto de revisão na descoberta eletrônica avançada

Quando o número de documentos coletados é grande, pode ser difícil examiná-los. A descoberta eletrônica avançada fornece várias ferramentas para analisar os documentos para reduzir o volume de documentos a serem revisados sem perda de informações e para ajudá-lo a organizar os documentos de forma coerente. Para saber mais sobre esses recursos, confira:

- [Próximo detecção duplicada](near-duplicate-detection-in-advanced-ediscovery.md)

- [Threading de emails](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

Para analisar dados em um conjunto de revisão:

1. Defina as configurações de análise para o seu caso. Para obter mais informações, consulte [Configurar definições de pesquisa e análise](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Abra o conjunto de revisão que você deseja analisar.

3. Clique em **gerenciar análise definida**.

4. Clique em **executar análise para o conjunto de revisão**.

Você pode verificar o progresso da análise na guia **trabalhos** da ocorrência.

 Após a conclusão da análise, você pode exibir o relatório de análise, executar consultas em seu conjunto de análise em saídas da análise (consulte [consulta dentro de seu conjunto de análise](review-set-search.md)) e ver documentos relacionados de um determinado documento (consulte [revisando dados no conjunto de revisão](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Relatório de análise

Para exibir um relatório de análise para um conjunto de análise:

1. Abra o conjunto de revisão.

2. Clique em **gerenciar análise definida**.

3. Clique em **Exibir relatório**.

O relatório tem sete componentes da análise:

- **População de destino:** O número de mensagens de email, anexos e documentos soltos encontrados no conjunto de revisão.

- **Documentos (exceto anexos):** O número de documentos soltos que são dinâmicos, exclusivos ou duplicados próximos de uma tabela dinâmica ou uma duplicata exata de outro documento.

- **Emails:** O número de mensagens de email inclusive, as cópias inclusivas, inclusive minuses ou nenhuma das opções acima.

- **Anexos:** O número de anexos de email exclusivos ou duplicados de outro anexo de email no conjunto de revisão.

- **Número de arquivos por tipo:** O número de arquivos, identificado pela extensão do arquivo.

- **Documentos por origem:** Um resumo do conteúdo pela fonte de dados original.

- **Documentos agregados por processo:** Um resumo do conteúdo por análise configurar processos. 
