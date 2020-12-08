---
title: Criar consultas de pesquisa na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Use palavras-chave e condições para restringir o escopo da pesquisa ao pesquisar dados usando a descoberta eletrônica avançada no Microsoft 365.
ms.openlocfilehash: 38322963f04ad67d8675247bdd754ffb1d2f13e8
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588548"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>Criar consultas de coleta de pesquisa na descoberta eletrônica avançada

Ao criar consultas de pesquisa para coletar dados em um caso de descoberta eletrônica avançada, você pode usar palavras-chave para localizar conteúdo e condições específicas para restringir o escopo da pesquisa para retornar itens que sejam mais relevantes para sua investigação legal.

![Usar palavras-chave e condições para restringir os resultados de uma pesquisa](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Pesquisas de palavra-chave

Digite uma consulta de palavra-chave na caixa **palavras-** chave na consulta de pesquisa. Você pode especificar palavras-chave, propriedades de mensagens de email, como datas enviadas e recebidas, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**. Você também pode pesquisar informações confidenciais (como números de seguridade social) em documentos no SharePoint e no OneDrive (não em mensagens de email) ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa **palavras-chave** vazia, todo o conteúdo localizado nos locais de conteúdo especificado estará nos resultados da pesquisa.

## <a name="keyword-list"></a>Lista de palavras-chave

Como alternativa, você pode marcar a caixa de seleção **Mostrar lista de palavras-chave** e a frase de palavra-chave ou palavra-chave digite em cada linha. As palavras-chave em cada linha são conectadas por um operador lógico (que é representado como *c:s* na sintaxe da consulta de pesquisa) que é semelhante em funcionalidade ao operador **or** na consulta de pesquisa criada. Isso significa que os itens que contêm qualquer palavra-chave em qualquer linha estão nos resultados da pesquisa. Você pode adicionar até 180 linhas na lista de palavras-chave em consultas avançadas de pesquisa de descoberta eletrônica.

![Use a lista de palavras-chave para obter estatísticas sobre cada palavra-chave na consulta](../media/KeywordListSearch.png)

Por que usar a lista de palavras-chave? Você pode obter estatísticas que mostram quantos itens correspondem a cada palavra-chave na lista de palavras-chave. Isso pode ajudá-lo a identificar rapidamente as palavras-chave mais (e menos) em vigor. Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha na lista de palavras-chave. Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).

## <a name="conditions"></a>Condições

Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é conectada logicamente à consulta de palavra-chave especificada na caixa palavra-chave por um operador lógico (que é representado como *c:c* na sintaxe da consulta de pesquisa) que é semelhante em funcionalidade ao operador **and** . Isso significa que os itens precisam satisfazer a consulta de palavra-chave e uma ou mais condições a serem incluídas nos resultados da pesquisa. É assim que as condições ajudam a restringir os resultados. Para obter uma lista e uma descrição das condições que você pode usar em uma consulta de pesquisa, consulte a seção "condições de pesquisa" em [consultas de palavra-chave e condições de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).
