---
title: Coletar dados para uma ocorrência na descoberta eletrônica avançada
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
description: Saiba como identificar um conjunto de documentos para revisão em uma investigação usando a ferramenta de pesquisa na descoberta eletrônica avançada.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956194"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Coletar dados para uma ocorrência na descoberta eletrônica avançada

Depois de identificar os responsáveis e as fontes de dados que são de interesse para o seu caso, é hora de identificar o conjunto de documentos para o qual se aprofundar. Você pode usar a ferramenta de pesquisa na descoberta eletrônica avançada para identificar documentos relevantes do custodial e locais não custodial no Microsoft 365.

Após executar uma pesquisa, você pode exibir estatísticas sobre os itens recuperados, como os locais que tinham a maioria dos itens que corresponderam à consulta de pesquisa. Você também pode visualizar um subconjunto dos resultados. Ao identificar o conjunto de documentos que você deseja examinar mais, você pode adicionar os resultados da pesquisa a uma revisão definida como coletar e processar.

## <a name="create-a-search"></a>Criar uma pesquisa

Selecionar **nova pesquisa** na guia **pesquisas** iniciará um assistente que orienta você durante a criação de uma pesquisa. Para obter informações detalhadas sobre como criar uma pesquisa, consulte [criar uma pesquisa para coletar dados](create-search-to-collect-data.md).

Após a criação de uma pesquisa, uma página de submenu com detalhes é exibida. Os botões de **estatísticas** e **Visualização** estão inicialmente indisponíveis porque a pesquisa ainda não foi concluída. Você pode acompanhar o progresso da pesquisa na guia **pesquisas** .

## <a name="view-search-results-and-statistics"></a>Exibir resultados e estatísticas de pesquisa

Há dois componentes de uma pesquisa de conteúdo: estatísticas (estimativas) e visualização. À medida que cada um desses componentes for concluído, você verá o status exibido nas colunas correspondentes na guia **pesquisas** mudar de **enviado** para **em andamento** para **concluído**.

Depois que a estimativa de pesquisa for concluída, selecione a pesquisa para exibir a página de submenu, que exibirá algumas estatísticas de alto nível sobre os resultados da pesquisa. Neste ponto, o botão **estatísticas** estará ativo. Você pode selecioná-lo para ver as estatísticas de pesquisa, como:

- Resumo
- Principais locais
- Consultas

Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).

Após a conclusão da visualização, o botão **Visualizar** estará ativo. Selecione-o para visualizar um subconjunto de amostra dos resultados.

## <a name="add-search-results-to-a-review-set"></a>Adicionar os resultados da pesquisa a um conjunto de revisão

Quando estiver pronto para coletar e processar os resultados inteiros de uma pesquisa, você poderá fazê-lo adicionando-o a um conjunto de revisão. Para obter detalhes, consulte [Adicionar dados a um conjunto de revisão](add-data-to-review-set.md).

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Adicionar dados que não sejam da Microsoft 365 a um conjunto de revisão

Como parte do processo de coleta para uma ocorrência, você também pode adicionar dados que não sejam do Office 365 a uma revisão de análise e análise e análise em conjunto com os dados do Office 365 que você coletou usando a ferramenta de pesquisa. Ao adicionar um não-Office 365, você precisa associá-lo a um funcionário específico no caso. Para obter mais informações, consulte [carregar dados não-Microsoft 365 em um conjunto de revisão](load-non-Office-365-data-into-a-review-set.md).
