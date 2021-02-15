---
title: Criar consultas de pesquisa na Descoberta Descoberta Avançada
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
description: Use palavras-chave e condições para restringir o escopo da pesquisa ao pesquisar dados usando a Descoberta Avançada no Microsoft 365.
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751108"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>Criar consultas de coleção de pesquisa no Advanced eDiscovery

Ao criar consultas de pesquisa para coletar dados em um caso de Descoberta Avançada, você pode usar palavras-chave para encontrar conteúdo e condições específicos para restringir o escopo da pesquisa e retornar itens que são mais relevantes para sua investigação legal.

![Usar palavras-chave e condições para restringir os resultados de uma pesquisa](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Pesquisas de palavra-chave

Digite uma consulta de palavra-chave na **caixa Palavras-chave** na consulta de pesquisa. Você pode especificar palavras-chave, propriedades de mensagens de email, como datas enviadas e recebidas, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**. Você também pode pesquisar informações confidenciais (como números de previdência social) em documentos no SharePoint e no OneDrive (não em mensagens de email) ou pesquisar documentos que foram compartilhados externamente. Se você deixar a **caixa Palavras-chave** vazia, todo o conteúdo localizado nos locais de conteúdo especificados está nos resultados da pesquisa.

## <a name="keyword-list"></a>Lista de palavras-chave

Como alternativa, você pode marcar a caixa **de** seleção Mostrar lista de palavras-chave e digitar uma palavra-chave ou frase de palavra-chave em cada linha. As palavras-chave em cada linha são conectadas por um operador lógico (que é representado como *c:s* na sintaxe de consulta de pesquisa) que é semelhante em funcionalidade ao operador **OR** na consulta de pesquisa criada. Isso significa que os itens que contêm qualquer palavra-chave em qualquer linha estão nos resultados da pesquisa. Você pode adicionar até 180 linhas na lista de palavras-chave nas consultas de pesquisa de Descobertas Avançadas.

![Usar a lista de palavras-chave para obter estatísticas sobre cada palavra-chave na consulta](../media/KeywordListSearch.png)

Por que usar a lista de palavras-chave? Você pode obter estatísticas que mostram quantos itens corresponderem a cada palavra-chave na lista de palavras-chave. Isso pode ajudá-lo a identificar rapidamente as palavras-chave que são mais (e menos) eficazes. Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha na lista de palavras-chave. Para obter mais informações sobre estatísticas de pesquisa, consulte [Estatísticas de pesquisa.](search-statistics-in-advanced-ediscovery.md)

## <a name="conditions"></a>Condições

Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave especificada na caixa de palavra-chave por um operador lógico (que é representado como *c:c* na sintaxe da consulta de pesquisa) que é semelhante em funcionalidade ao operador **AND.** Isso significa que os itens devem atender à consulta de palavra-chave e a uma ou mais condições a serem incluídos nos resultados da pesquisa. É assim que as condições ajudam a restringir os resultados. Para uma lista e uma descrição das condições que você pode usar em uma consulta de pesquisa, consulte a seção "Condições de pesquisa" em Consultas de palavra-chave e condições [de pesquisa.](keyword-queries-and-search-conditions.md#search-conditions)
