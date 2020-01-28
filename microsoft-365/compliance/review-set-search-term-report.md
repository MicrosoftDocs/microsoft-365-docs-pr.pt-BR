---
title: Gerar relatório de termo de pesquisa para um conjunto de revisão
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: bb65745f92d1f77e6cc3224832c0a9871e567ca5
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558468"
---
# <a name="generate-search-term-report-for-a-review-set"></a>Gerar relatório de termo de pesquisa para um conjunto de revisão

Na descoberta eletrônica, uma das condições usadas com mais frequência para consultar documentos é usar termos de pesquisa de palavra-chave. Identificando documentos que contenham as palavras-chave específicas (também conhecidas como *termos*) que são importantes para um caso, os revisores podem começar a obter uma compreensão de alto nível do que estão enfrentando. Em descoberta eletrônica avançada no Microsoft 365, você pode fazer isso precisamente gerando relatórios de termos de pesquisa em consultas salvas em um conjunto de revisão.

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>Etapa 1: criar uma consulta salva no conjunto de revisão

Para gerar um relatório de termo de pesquisa significativo, crie uma consulta salva que define o conjunto de documentos no conjunto de revisão para o qual você deseja gerar um relatório de termos de pesquisa. Por exemplo, você pode usar um intervalo de datas ou o conjunto real de termos de pesquisa (usando o cartão de condição de palavras-chave) para criar a consulta. Para saber mais sobre as consultas set de revisão, confira [consultar os dados em um conjunto de revisão](review-set-search.md).

## <a name="step-2-generate-a-search-term-report"></a>Etapa 2: gerar um relatório de termos de pesquisa

Há duas maneiras diferentes de gerar um relatório de termos de pesquisa: por meio do menu de contexto da consulta salva que você criou na etapa 1 ou do console de gerenciamento de relatório de termos de pesquisa.

- Para usar o menu de contexto, abra o menu de contexto da consulta salva que você criou na etapa 1 e clique em **gerar relatório de termos de pesquisa**.

- Para usar o console de gerenciamento, vá para **gerenciar análise definir > exibir relatórios de termos de pesquisa**, clique em **novo**e selecione a consulta salva que você criou na etapa 1.

Em seguida, insira os termos que você gostaria de relatar, separados por nova linha; se a consulta salva que você criou na etapa 1 cartão de condição de palavra-chave usada, a página de submenu será preenchida com os termos do cartão de condição de primeira palavra-chave usado na consulta salva.

Em seguida, selecione até três dinâmicas para relatar e clique em **gerar**, que iniciará o trabalho de geração de relatórios de termos de pesquisa.

### <a name="what-is-a-pivot"></a>O que é uma tabela dinâmica?

Os pivôs são como o relatório será organizado. Considere o exemplo seguinte.

- A consulta salva recupera 10 documentos: doc1 a doc10.

- doc1, Doc2, Doc3, Doc4, doc5, doc6 e doc7 contêm o termo "eDiscovery".

- doc6, doc7, doc8, doc9 e doc10 contêm o termo "investigação".

- doc1, Doc3, doc5, doc7, doc9 são de responsáveis por.

- Doc2, Doc4, doc6, doc8, doc10 são de responsáveis por ISB.

Nesse caso, se você fosse gerar um relatório de termos de pesquisa nos termos "eDiscovery" e "investigação" e dinamizar os responsáveis, o relatório de termos de pesquisa será organizado da seguinte maneira:

- "eDiscovery"-responsáveis: 4 documentos

- "eDiscovery"-responsáveis B: 3 documentos

- "Investigação"-responsáveis: 2 documentos

- "Investigação"-responsáveis B: 3 documentos

## <a name="step-3-download-report"></a>Etapa 3: baixar o relatório

No console de gerenciamento de termos de pesquisa, você pode acompanhar o status de um trabalho de relatório de um termo de pesquisa criado anteriormente. Depois que o trabalho for concluído, você poderá clicar na linha do relatório de termos de pesquisa e clicar em "download", que baixará o relatório de termos de pesquisa em um formato CSV. Haverá uma linha por (Pesquisar termo, pivots) tupla e cada linha conterá as seguintes informações:

- Quantos documentos foram recuperados?

- Quantas vezes o termo de pesquisa foi encontrado nos documentos?

- Qual é o volume total de documentos recuperados?

- Quantas famílias foram recuperadas?

- Qual é a contagem total de documentos dessas famílias, incluindo os documentos que não tinham o termo de pesquisa?

- Qual é o volume total dos anteriores?