---
title: Consultar dados em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como criar e executar uma consulta em uma revisão definida para organizar dados para uma análise mais eficiente em uma ocorrência de descoberta eletrônica avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816564"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar dados em um conjunto de revisão

Na maioria dos casos, será útil ser capaz de se aprofundar nos dados de um conjunto de análise e organizar esses dados para facilitar uma análise mais eficiente. Usar consultas em um conjunto de revisão ajuda você a se concentrar em um subconjunto de documentos que atendem aos critérios de sua análise.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Criando e executando uma consulta em um conjunto de revisão

Para criar e executar uma consulta nos documentos em um conjunto de revisão, selecione **nova consulta** no conjunto de revisão. Depois de nomear sua consulta e definir as condições, selecione **salvar** para salvar e executar a consulta. Para executar uma consulta que tenha sido salva anteriormente, selecione uma consulta salva.

![Analisar consultas de definição](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Criar uma consulta de conjunto de revisão

Você pode criar uma consulta usando uma combinação de palavras-chave, propriedades e condições na condição de palavras-chave. Você também pode agrupar as condições como um bloco (chamado de *grupo de condição* ) para criar uma consulta mais complexa. Para obter uma lista e uma descrição das propriedades de metadados que você pode pesquisar, confira os [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condições

Cada campo pesquisável em um conjunto de revisão tem uma condição correspondente que você pode usar para criar sua consulta.

Há vários tipos de condições:

- FREETEXT: uma condição freetext é usada para campos de texto como assunto. Você pode listar vários termos de pesquisa separando-os com uma vírgula.

- Date: uma condição de data é usada para campos de data, como data da última modificação.

- Opções de pesquisa: uma condição de opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico em seu conjunto de análise. Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de análise.

- Palavra-chave: uma condição de palavra-chave é uma instância específica da condição FREETEXT que você pode usar para pesquisar termos ou usar o idioma de consulta do KQL como no. Veja mais detalhes abaixo.

### <a name="query-language"></a>Linguagem de consulta

Além das condições, você pode usar um idioma de consulta semelhante a KQL na condição de palavras-chave para compilar sua consulta. A linguagem de consulta para consultas de conjunto de revisão oferece suporte a operadores booleanos padrão, como **e** , **ou** , e **não** , e **Near** . Também suporta um curinga de caractere único (?) e um curinga de vários caracteres (*).

## <a name="filters"></a>Filtros

Além das consultas que podem ser salvas, você pode usar os filtros de definição de análise para aplicar rapidamente condições adicionais a uma consulta de conjunto de revisão. O uso de filtros ajuda você a refinar ainda mais os resultados exibidos por uma consulta de conjunto de revisão.

![Examinar filtros de conjunto](../media/AeDReviewSetFilters.png)

Os filtros diferem das consultas de duas maneiras significativas:

- Os filtros são transitórios. Eles não persistem além da sessão existente. Em outras palavras, não é possível salvar um filtro. As consultas são salvas no conjunto de revisão e acessadas sempre que abrir o conjunto de revisão.

- Os filtros são sempre aditivos. Os filtros são aplicados além da consulta do conjunto de análise atual. A aplicação de uma consulta diferente substituirá os resultados retornados pela consulta atual.
