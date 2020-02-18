---
title: Criar consultas de pesquisa
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
description: Use palavras-chave e condições para restringir o escopo de pesquisa ao pesquisar dados usando a investigação de dados no Microsoft 365.
ms.openlocfilehash: b6769d662f843622a537a5ce93c1c5331b00fc3f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079010"
---
# <a name="build-search-queries"></a>Criar consultas de pesquisa

Ao criar consultas de pesquisa, você pode usar palavras-chave para localizar conteúdo e condições específicas para restringir o escopo da pesquisa para retornar itens que sejam mais relevantes para sua investigação.

![Usar palavras-chave e condições para restringir os resultados de uma pesquisa](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Pesquisas de palavra-chave

Digite uma consulta de palavra-chave na caixa **palavras-** chave na consulta de pesquisa. Você pode especificar palavras-chave, propriedades de mensagens de email, como datas enviadas e recebidas, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**. Você também pode pesquisar informações confidenciais, como números de seguridade social, em documentos no SharePoint e no OneDrive (não em mensagens de email) ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa **palavras-chave** vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa.
    
Como alternativa, você pode marcar a caixa de seleção **Mostrar lista de palavras-chave** e digitar uma frase de palavra-chave ou palavra-chave em cada linha. Se você fizer isso, as palavras-chave em cada linha serão conectadas por um operador lógico (representado como *c:s*) que é semelhante em funcionalidade ao operador **or** na consulta de pesquisa criada. Isso significa que os itens que contêm qualquer palavra-chave em qualquer linha são incluídos nos resultados da pesquisa.

![Use a lista de palavras-chave para obter estatísticas sobre cada palavra-chave na consulta](../media/KeywordListSearch.png)

Por que usar a lista de palavras-chave? Você pode obter estatísticas que mostram quantos itens correspondem a cada palavra-chave na lista de palavras-chave. Isso pode ajudá-lo a identificar rapidamente as palavras-chave mais (e menos) em vigor. Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha na lista de palavras-chave. Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).

> [!NOTE]
> Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, você está limitado a um máximo de 20 linhas na lista de palavras-chave.

## <a name="conditions"></a>Condições
    
Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é conectada logicamente à consulta de palavra-chave (especificada na caixa palavra-chave) por um operador lógico (que é representado como *c:c*) que é semelhante em funcionalidade ao operador **and** . Isso significa que os itens precisam satisfazer a consulta de palavra-chave e uma ou mais condições a serem incluídas nos resultados da pesquisa. É assim que as condições ajudam a restringir os resultados. Para obter uma lista e uma descrição das condições que você pode usar em uma consulta de pesquisa, consulte a seção "condições de pesquisa" em [consultas de palavra-chave e condições de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).
