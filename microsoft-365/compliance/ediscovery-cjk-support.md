---
title: Suporte A CJK/Byte Duplo para Descoberta Avançada
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
description: Saiba como a Descoberta Avançada no Microsoft 365 dá suporte a idiomas chineses, japoneses e coreanos (CJK), que usam um conjunto de caracteres de byte duplo.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926597"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Suporte a idioma CJK para Descoberta Avançada

A Descoberta Pública Avançada dá suporte a idiomas de conjunto de caracteres de byte duplo (eles incluem chinês simplificado, chinês tradicional, japonês e coreano, que são coletivamente conhecidos como idiomas *CJK)* para os seguintes cenários avançados em um conjunto de revisão:

- Quando você [consulta os dados em um conjunto de revisão.](review-set-search.md)

- Quando você [marca documentos em um conjunto de revisão](tagging-documents.md).

- Quando você [analisa dados de caso em um conjunto de](analyzing-data-in-review-set.md) revisão usando a detecção quase duplicada, threading de email e análise de temas.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como criar uma pesquisa para coletar itens que contenham caracteres CJK?**

Você pode usar caracteres [](building-search-queries.md#keyword-searches)CJK para pesquisas de palavra-chave, consultas de [palavra-chave](keyword-queries-and-search-conditions.md) e condições de pesquisa ao pesquisar conteúdo em Descoberta Avançada. A pesquisa de caracteres CJK também é suportada ao pesquisar conteúdo no Core eDiscovery and Content Search.

Fornecemos suporte a CJK para todos os operadores de pesquisa e condições de pesquisa [,](keyword-queries-and-search-conditions.md#search-conditions)incluindo os operadores booleanos **AND**, **OR**, **NOT** e **NEAR**. [](keyword-queries-and-search-conditions.md#search-operators)

Se você tiver certeza de que os locais ou itens de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando resultados, clique no ícone idioma de consulta-país/região ![Ícone de país/região de idioma de consulta na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selecione o valor de código de cultura de idioma-país correspondente para a pesquisa. O padrão idioma/região é neutro.

**Posso pesquisar vários idiomas ao mesmo tempo?**

Depende do cenário de pesquisa.

- Ao [consultar dados em um](review-set-search.md) conjunto de revisão na Descoberta Avançada, você pode pesquisar vários idiomas.

- Ao criar [uma pesquisa para coletar dados,](create-search-to-collect-data.md)crie uma pesquisa separada para cada idioma que você está direcionando. Por exemplo, se você estiver procurando por um documento que contenha chinês e coreano, selecione Chinês para sua primeira consulta e selecione Coreano para sua segunda consulta.

**Não vejo o ícone de idioma de consulta país/região para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma pesquisa de conjunto de revisão?**

Para consultar o conjunto de revisão, você não precisa especificar um idioma de documento. A Descoberta Automática Avançada detecta automaticamente idiomas de documento quando você adiciona conteúdo a um conjunto de revisão. Isso ajuda você a otimizar os resultados da consulta em um conjunto de revisão.

**Posso ver idiomas detectados em [metadados de arquivo?](view-documents-in-review-set.md#file-metadata)**

Não, você não pode ver idiomas detectados em metadados de arquivo.

**Posso filtrar por idiomas de documento em um conjunto de revisão?**

Não, você não pode filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.

**Essa versão CJK para cenários de conjunto de revisão afetará qualquer um dos meus conjuntos de pesquisa e revisão existentes?**

Não, nenhuma das suas pesquisas e conjuntos de revisão existentes será mudada. Você não precisa reindexar dados existentes, e os resultados da pesquisa para texto em inglês serão os mesmos.

**Como altero meu idioma de exibição para chinês, japonês ou coreano?**

Para obter informações sobre como alterar o idioma de exibição e o fuso horário, consulte Como definir configurações de idioma e região [para o Office 365](/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemas conhecidos

- O OCR não dá suporte a caracteres CJK de arquivos de imagem

- Arquivos de email (como *.eml e *.msg) no exibição [Anotações](view-documents-in-review-set.md#annotate-view) não são suportados para idiomas CJK.

- O realce de acerto de pesquisa no [exibição Texto](view-documents-in-review-set.md#text-view) não é suportado para idiomas CJK.

- O [módulo De](using-relevance.md) relevância usado para analisar dados não dá suporte a idiomas CJK.

- [Os respaldos baseados](managing-holds.md#manage-non-custodial-holds) em consultas não são suportados para idiomas CJK.