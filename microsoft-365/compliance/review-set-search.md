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
description: Saiba como criar e executar uma consulta em um conjunto de revisão para organizar dados para uma revisão mais eficiente em um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345795"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar dados em um conjunto de revisão

Na maioria dos casos, será útil ser capaz de aprofundar os dados em um conjunto de revisão e organizar esses dados para facilitar uma revisão mais eficiente. Usar consultas em um conjunto de revisão ajuda você a se concentrar em um subconjunto de documentos que atendem aos critérios de sua revisão.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Criar e executar uma consulta em um conjunto de revisão

Para criar e executar uma consulta nos documentos em um conjunto de revisão, selecione **Nova consulta** no conjunto de revisão. Depois de nomear sua consulta e definir as condições, selecione **Salvar** para salvar e executar a consulta. Para executar uma consulta que foi salva anteriormente, selecione uma consulta salva.

![Revisar consultas de conjunto](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Criando uma consulta de conjunto de revisão

Você pode criar uma consulta usando uma combinação de palavras-chave, propriedades e condições na condição Keywords. Você também pode agrupar condições como um bloco (chamado de grupo de *condição*) para criar uma consulta mais complexa. Para uma lista e uma descrição das propriedades de metadados que você pode pesquisar, consulte [Campos de metadados do documento no](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condições

Cada campo pesquisável em um conjunto de revisão tem uma condição correspondente que você pode usar para criar sua consulta.

Há vários tipos de condições:

- Freetext: Uma condição de texto livre é usada para campos de texto, como assunto. Você pode listar vários termos de pesquisa separando-os com uma vírgula.

- Data: uma condição de data é usada para campos de data, como a última data modificada.

- Opções de pesquisa: uma condição de opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico no conjunto de revisão. Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de revisão.

- Palavra-chave: uma condição de palavra-chave é uma instância específica da condição de texto livre em que você pode usar para pesquisar termos ou usar linguagem de consulta do tipo KQL. Consulte abaixo para obter mais detalhes.

### <a name="query-language"></a>Linguagem de consulta

Além das condições, você pode usar um idioma de consulta parecido com KQL na condição Palavras-chave para criar sua consulta. O idioma de consulta para consultas de conjunto de revisão dá suporte a operadores booleano padrão, como **AND**, **OR**, **NOT** e **NEAR**. Ele também dá suporte a um caractere curinga de caractere único (?) e a um caractere curinga de vários caracteres (*).

## <a name="filters"></a>Filtros

Além das consultas que você pode salvar, você pode usar filtros de conjunto de revisão para aplicar rapidamente condições adicionais a uma consulta de conjunto de revisão. O uso de filtros ajuda você a refinar ainda mais os resultados exibidos por uma consulta de conjunto de revisão.

![Revisar filtros de conjunto](../media/AeDReviewSetFilters.png)

Os filtros diferem das consultas de duas maneiras significativas:

- Os filtros são transitórios. Eles não persistem além da sessão existente. Em outras palavras, você não pode salvar um filtro. As consultas são salvas no conjunto de revisão e acessam-nas sempre que você abre o conjunto de revisão.

- Os filtros são sempre aditivos. Os filtros são aplicados além da consulta de conjunto de revisão atual. A aplicação de uma consulta diferente substituirá os resultados retornados pela consulta atual.
