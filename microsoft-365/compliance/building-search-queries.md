---
title: Criar consultas de pesquisa em Advanced eDiscovery
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
description: Use palavras-chave e condições para restringir o escopo da pesquisa ao pesquisar dados usando Advanced eDiscovery em Microsoft 365.
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838474"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a>Criar consultas de pesquisa para coleções em Advanced eDiscovery

Ao configurar [a](collections-overview.md) consulta de pesquisa ao criar uma coleção em um caso de Advanced eDiscovery, você pode usar palavras-chave para encontrar conteúdo e condições específicos para restringir o escopo da pesquisa para retornar itens mais relevantes à investigação legal.

![Usar palavras-chave e condições para restringir os resultados de uma pesquisa](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Pesquisas de palavras-chave

Digite uma consulta de palavra-chave na caixa **Palavras-chave** na consulta de pesquisa. Você pode especificar palavras-chave, propriedades de mensagem de email, como datas enviadas e recebidas, ou propriedades de documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, como **E**, **OU**, **NÃO** e **PRÓXIMO**. Você também pode pesquisar informações confidenciais (como números de segurança social) em documentos em SharePoint e OneDrive (não em mensagens de email) ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa **Palavras-chave** vazia, todo o conteúdo nos locais de conteúdo especificado aparecerá nos resultados da pesquisa.

## <a name="keyword-list"></a>Lista de palavras-chave

Como alternativa, você pode selecionar a caixa de seleção **Mostrar** lista de palavras-chave e o tipo de palavra-chave ou frase de palavra-chave em cada linha. As palavras-chave em cada linha são conectadas por um operador lógico (que é representado como *c:s* na sintaxe de consulta de pesquisa) que é semelhante em funcionalidade ao operador **OR** na consulta de pesquisa criada. Isso significa que os itens que contêm qualquer palavra-chave em qualquer linha estão nos resultados da pesquisa. Você pode adicionar até 180 linhas na lista de palavras-chave em Advanced eDiscovery de pesquisa.

![Use a lista de palavras-chave para obter estatísticas sobre cada palavra-chave na consulta](../media/KeywordListSearch.png)

Por que usar a lista de palavras-chave? Você pode obter estatísticas que mostram quantos itens corresponderão a cada palavra-chave na lista de palavras-chave. Isso pode ajudá-lo a identificar rapidamente as palavras-chave que são mais (e menos) eficazes. Você também pode usar uma frase de palavra-chave (cercada por parênteses) em uma linha na lista de palavras-chave. Para obter mais informações sobre estatísticas de pesquisa, consulte [Search statistics](search-statistics-in-advanced-ediscovery.md).

## <a name="conditions"></a>Condições

Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto mais refinado de resultados. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave especificada na caixa de palavra-chave por um operador lógico (que é representado como *c:c* na sintaxe de consulta de pesquisa) que é semelhante na funcionalidade ao operador **AND.** Isso significa que os itens devem atender à consulta de palavra-chave e a uma ou mais condições a serem incluídas nos resultados da pesquisa. É assim que as condições ajudam a restringir os resultados. Para uma lista e descrição das condições que você pode usar em uma consulta de pesquisa, consulte a seção "Condições de pesquisa" em Consultas de palavra-chave e condições [de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).
