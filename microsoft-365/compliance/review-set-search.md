---
title: Consultar os dados em um conjunto de revisão
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
description: ''
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073770"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar os dados em um conjunto de revisão

Na maioria dos casos, será útil ser capaz de se aprofundar no que está em um conjunto de revisão e organizá-los para análise mais eficiente. As consultas em um conjunto de revisão permitem que você faça isso, permitindo que você se concentre em um subconjunto de documentos que atendem aos critérios definidos por você ao mesmo tempo.

## <a name="creating-and-running-a-query-within-a-review-set"></a>Criar e executar uma consulta dentro de um conjunto de revisão

Para criar e executar uma consulta no conjunto de análise, clique em "nova consulta" em seu conjunto de revisão. Depois de nomear sua consulta e definir as condições, clique em "salvar" para executar a consulta. Para executar uma consulta que tenha sido salva anteriormente, basta clicar na consulta salva. Consulte os [campos de metadados do documento](document-metadata-fields.md) para obter uma lista de metadados que você pode pesquisar.

## <a name="building-your-query"></a>Criar sua consulta

Você pode criar sua consulta usando uma combinação de cartões de condição e linguagem de consulta no cartão de condição de palavras-chave. Você pode agrupar cartões de condição juntos como um bloco para criar uma consulta mais complexa.

### <a name="condition-card"></a>Cartão de condição

Cada campo pesquisável em um conjunto de revisão tem um cartão de condição correspondente que você pode usar para criar sua consulta.

Há vários tipos de cartões de condição:
- FREETEXT: o cartão de condição do freetext é usado para campos de texto como o assunto. Você pode listar vários termos de pesquisa separando-os com uma vírgula.
- Date: o cartão de condição de data é usado para campos de data, como data da última modificação.
- Opções de pesquisa: o cartão de condição opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico em seu conjunto de análise. Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de análise.
- Palavra-chave: cartão de condição de palavra-chave é uma instância específica do cartão de condição FREETEXT que você pode usar para pesquisar termos ou usar o idioma de consulta do KQL. Veja mais detalhes abaixo.

### <a name="query-language"></a>Linguagem de consulta

Além de cartões de condição, você pode usar um idioma de consulta do tipo KQL no cartão de palavras-chave para criar sua consulta. A linguagem de consulta oferece suporte à sintaxe KQL padrão como e, ou, não e NEAR (n). Também suporta curingas de caractere único (?) e curinga de vários caracteres (*).

## <a name="filter"></a>Filtrar

Além das consultas que você pode salvar, você pode sobrepor mais condições de imediato aos resultados da consulta usando filtros. Os filtros diferem das consultas de algumas maneiras significativas:
- Os filtros são temporários (ou seja, não persistem em diferentes sessões), enquanto as consultas são salvas no conjunto de revisão.
- Os filtros são sempre aditivos; os filtros serão aplicados na parte superior da consulta que você tem em vigor no momento, ao passo que a aplicação de uma consulta substituirá a consulta em vigor.