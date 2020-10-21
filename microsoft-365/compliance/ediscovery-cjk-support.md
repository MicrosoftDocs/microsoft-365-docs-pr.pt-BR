---
title: Suporte de CJK/dobrar bytes para descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como a descoberta eletrônica avançada no Microsoft 365 suporta idiomas em chinês, japonês e coreano (CJK), que usam um conjunto de caracteres de byte duplo.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626928"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Suporte a idiomas CJK para descoberta eletrônica avançada

A descoberta eletrônica avançada oferece suporte a idiomas de conjunto de caracteres de byte duplo (eles incluem chinês simplificado, chinês tradicional, japonês e coreano, coletivamente conhecidos como idiomas *CJK* ) para os seguintes cenários avançados em um conjunto de análise:

- Quando você [consulta os dados em um conjunto de revisão](review-set-search.md).

- Quando você [marca documentos em um conjunto de revisão](tagging-documents.md).

- Quando você [analisa dados de caso em um conjunto de revisão usando a](analyzing-data-in-review-set.md) detecção próxima duplicação, encadeamento de email e análise de temas.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como faço para criar uma pesquisa para coletar itens que contenham caracteres CJK?**

Você pode usar caracteres CJK para [pesquisas de palavra-](building-search-queries.md#keyword-searches)chave, [consultas de palavra-chave e condições de pesquisa](keyword-queries-and-search-conditions.md) ao pesquisar conteúdo na descoberta eletrônica avançada. A pesquisa por caracteres CJK também é suportada durante a pesquisa de conteúdo na descoberta eletrônica principal e pesquisa de conteúdo.

Oferecemos suporte a CJK para todos [os operadores de pesquisa](keyword-queries-and-search-conditions.md#search-operators) e condições de [pesquisa](keyword-queries-and-search-conditions.md#search-conditions), incluindo os operadores booleanos **e**, **ou**, **não**e **próximos**.

Se você tiver certeza de que os itens ou os locais de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando nenhum resultado, clique no ícone idioma da consulta-país/região ![Idioma da consulta-ícone de país/região na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selecione o valor de código de cultura do idioma-país correspondente para a pesquisa. O padrão idioma/região é neutro.

**Posso pesquisar vários idiomas de uma só vez?**

Depende do seu cenário de pesquisa.

- Ao [consultar dados em um conjunto de análise](review-set-search.md) na descoberta eletrônica avançada, você pode pesquisar vários idiomas.

- Ao [criar uma pesquisa para coletar dados](create-search-to-collect-data.md), crie uma pesquisa separada para cada idioma para o qual você está direcionado. Por exemplo, se você estiver procurando um documento que contenha chinês e coreano, selecione chinês para a primeira consulta e selecione coreano para a segunda consulta.

**Não vejo o ícone de idioma de consulta-país/região para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma análise definir pesquisa?**

Para consultas de conjunto de revisão, não é necessário especificar um idioma de documento. A descoberta eletrônica avançada detecta idiomas de documento automaticamente quando você adiciona conteúdo a um conjunto de revisão. Isso ajuda a otimizar os resultados da consulta em um conjunto de revisão.

**Posso ver os idiomas detectados nos [metadados do arquivo](view-documents-in-review-set.md#file-metadata)?**

Não, não é possível ver idiomas detectados nos metadados do arquivo.

**Posso filtrar por idiomas de documento em um conjunto de revisão**?

Não, não é possível filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.

**Este lançamento CJK para cenários de análise definida afetará qualquer uma das minhas pesquisas existentes e conjuntos de revisão?**

Não, nenhum dos conjuntos de pesquisas e de revisão existentes será alterado. Você não precisa reindexar os dados existentes e os resultados de pesquisa do texto em inglês serão os mesmos.

**Como altero meu idioma de exibição para chinês, japonês ou coreano?**

Para obter informações sobre como alterar o idioma de exibição e o fuso horário, consulte [como definir configurações de idioma e região para o Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemas conhecidos

- O OCR não dá suporte a caracteres CJK de arquivos de imagem

- Arquivos de email (como *. eml e *. msg) no [modo de anotações](view-documents-in-review-set.md#annotate-view) não têm suporte para idiomas CJK.

- O realce de ocorrências de pesquisa no [modo de texto](view-documents-in-review-set.md#text-view) não tem suporte em idiomas CJK.

- O [módulo de relevância](using-relevance.md) usado para analisar dados não é compatível com idiomas CJK.

- Não há suporte para o [bloqueio baseado em consulta](managing-holds.md#manage-non-custodial-holds) em idiomas CJK. 
