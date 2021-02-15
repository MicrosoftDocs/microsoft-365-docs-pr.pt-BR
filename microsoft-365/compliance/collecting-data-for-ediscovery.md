---
title: Coletar dados para uma ocorrência na Descoberta Avançada
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
description: Saiba como identificar um conjunto de documentos para revisão em uma investigação usando a ferramenta Pesquisa na Descoberta Avançada.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751259"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Coletar dados para uma ocorrência na Descoberta Avançada

Depois de identificar os custodiantes e as fontes de dados que são de interesse para o seu caso, é hora de identificar o conjunto de documentos no qual se aprofundar. Você pode usar a ferramenta de Pesquisa na Descoberta Avançada para identificar documentos relevantes de locais de custodiante e não custodial no Microsoft 365.

Depois de executar uma pesquisa, você pode exibir estatísticas nos itens recuperados, como os locais que tinham a maioria dos itens que corresponderam à consulta de pesquisa. Você também pode visualizar um subconjunto dos resultados. Quando você identificar o conjunto de documentos que deseja examinar ainda mais, poderá adicionar os resultados da pesquisa a um conjunto de revisão a ser coletar e processar.

## <a name="create-a-search"></a>Criar uma pesquisa

Selecionar **Nova pesquisa** na guia **Pesquisas** iniciará um assistente que o orienta na criação de uma pesquisa. Para obter informações detalhadas sobre como criar uma pesquisa, consulte [Criar uma pesquisa para coletar dados.](create-search-to-collect-data.md)

Depois que uma pesquisa é criada, uma página de sobremenu com detalhes é exibida. Os **botões Estatísticas** e **Visualização** estão inicialmente indisponíveis porque a pesquisa ainda não foi concluída. Você pode acompanhar o progresso da pesquisa na **guia** Pesquisas.

## <a name="view-search-results-and-statistics"></a>Exibir resultados e estatísticas de pesquisa

Há dois componentes de uma pesquisa de conteúdo: Estatísticas (Estimativas) e Visualização. Conforme cada um desses componentes é concluído, você verá o  status exibido nas colunas correspondentes na guia Pesquisas mudar de **Submitted** to **In progress** to **Completed**.

Depois que a estimativa de pesquisa for concluída, selecione a pesquisa para exibir a página do sub88, que exibirá algumas estatísticas de alto nível sobre os resultados da pesquisa. Neste ponto, o **botão Estatísticas** estará ativo. Você pode selecioná-la para ver as estatísticas de pesquisa, como:

- Resumo
- Principais locais
- Consultas

Para obter mais informações sobre estatísticas de pesquisa, consulte [Estatísticas de pesquisa.](search-statistics-in-advanced-ediscovery.md)

Depois que a visualização for concluída, o **botão** Visualizar estará ativo. Selecione-o para visualizar um subconjunto amostrado dos resultados.

## <a name="add-search-results-to-a-review-set"></a>Adicionar os resultados da pesquisa a um conjunto de revisão

Quando você estiver pronto para coletar e processar todos os resultados de uma pesquisa, poderá fazer isso adicionando-o a um conjunto de revisão. Para obter detalhes, [consulte Adicionar dados a um conjunto de revisão.](add-data-to-review-set.md)

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Adicionar dados que não são do Microsoft 365 a um conjunto de revisão

Como parte do processo de coleta de um caso, você também pode adicionar dados que não são do Office 365 a um conjunto de revisão, analisar e analisar junto com os dados do Office 365 coletados usando a ferramenta de pesquisa. Ao adicionar um não-Office 365, você precisa associá-lo a um custodiante específico no caso. Para obter mais informações, [consulte Carregar dados que não são do Microsoft 365 em um conjunto de revisão.](load-non-Office-365-data-into-a-review-set.md)
