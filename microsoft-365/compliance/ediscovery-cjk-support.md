---
title: Suporte a CJK/Byte duplo para Descoberta Avançada
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
description: Saiba como a Descoberta Avançada no Microsoft 365 dá suporte a idiomas em chinês, japonês e coreano (CJK), que usam um conjunto de caracteres de dois byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626928"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Suporte à linguagem CJK para Descoberta Avançada

A Descoberta Avançada dá suporte a idiomas de conjunto de caracteres de byte duplo (incluem chinês simplificado, chinês tradicional, japonês e coreano, que são coletivamente conhecidos como idiomas *CJK)* para os seguintes cenários avançados em um conjunto de revisão:

- Quando você [consultar os dados em um conjunto de revisão.](review-set-search.md)

- Quando você [marca documentos em um conjunto de revisão.](tagging-documents.md)

- Ao analisar [dados de caso em um conjunto de revisão usando](analyzing-data-in-review-set.md) a detecção quase duplicada, threading de email e análise de temas.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como criar uma pesquisa para coletar itens que contenham caracteres CJK?**

Você pode usar caracteres CJK [](keyword-queries-and-search-conditions.md) para pesquisas de palavra-chave, [](building-search-queries.md#keyword-searches)consultas de palavra-chave e condições de pesquisa ao pesquisar conteúdo na Descoberta Avançada. A pesquisa de caracteres CJK também é suportada durante a pesquisa de conteúdo na Descoberta Principal e na Pesquisa de Conteúdo.

Fornecemos suporte A CJK para todos os operadores de pesquisa e condições de pesquisa , incluindo os operadores boolários **AND**, **OR**, **NOT** e **NEAR**. [](keyword-queries-and-search-conditions.md#search-operators) [](keyword-queries-and-search-conditions.md#search-conditions)

Se você tiver certeza de que os locais ou itens de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando resultados, clique no ícone de idioma/região da consulta ![Ícone de idioma/país/região de consulta na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selecione o valor de código de cultura de país/idioma correspondente para a pesquisa. O padrão idioma/região é neutro.

**Posso pesquisar vários idiomas ao mesmo tempo?**

Depende do cenário de pesquisa.

- Ao consultar [dados em um conjunto de revisão](review-set-search.md) na Descoberta Avançada, você pode pesquisar vários idiomas.

- Ao criar [uma pesquisa para coletar dados,](create-search-to-collect-data.md)crie uma pesquisa separada para cada idioma que você está direcionando. Por exemplo, se você estiver procurando um documento que contenha chinês e coreano, selecione chinês para sua primeira consulta e selecione coreano para a segunda consulta.

**Não vejo o ícone de idioma/país/região de consulta para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma pesquisa de conjunto de revisão?**

Para consultas de conjunto de revisão, você não precisa especificar um idioma de documento. A Descoberta Automática Avançada detecta automaticamente idiomas de documentos quando você adiciona conteúdo a um conjunto de revisão. Isso ajuda a otimizar os resultados da consulta em um conjunto de revisão.

**Posso ver idiomas detectados nos [metadados de arquivo?](view-documents-in-review-set.md#file-metadata)**

Não, você não pode ver idiomas detectados nos metadados do arquivo.

**Posso filtrar por idiomas de documento em um conjunto de revisão?**

Não, você não pode filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.

**Essa versão do CJK para cenários de conjunto de revisão afetará qualquer um dos meus conjuntos de pesquisa e revisão existentes?**

Não, nenhum dos conjuntos de pesquisa e revisão existentes mudará. Você não precisa reindexar dados existentes e os resultados da pesquisa para texto em inglês serão os mesmos.

**Como altero meu idioma de exibição para chinês, japonês ou coreano?**

Para saber mais sobre como alterar o idioma de exibição e o fuso horário, confira Como definir configurações de idioma e região para [o Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>Problemas conhecidos

- O OCR não dá suporte a caracteres CJK de arquivos de imagem

- Arquivos de email (como *.eml e *.msg) na exibição Anotação não são suportados para idiomas CJK. [](view-documents-in-review-set.md#annotate-view)

- O realce de acertos de pesquisa [no visualização](view-documents-in-review-set.md#text-view) texto não é suportado para idiomas CJK.

- O [módulo de Relevância](using-relevance.md) usado para analisar dados não dá suporte a linguagens CJK.

- [Não há suporte para retém](managing-holds.md#manage-non-custodial-holds) baseados em consulta para idiomas CJK. 
