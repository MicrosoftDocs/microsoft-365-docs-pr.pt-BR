---
title: Adicionar dados de um conjunto de revisão para outro conjunto de revisão
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
ms.openlocfilehash: bd33d57380e99225d741b9c38677c2b49694139a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072379"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Adicionar dados a um conjunto de revisão de outro conjunto de revisão

Em alguns casos, pode ser necessário distribuir uma parte dos documentos de um conjunto de análise e trabalhar com eles individualmente em outro conjunto de revisão.  Isso é especialmente útil se você tiver escolhido conteúdo em um conjunto de revisão e quiser executar a análise no subconjunto de dados.

Siga o fluxo de trabalho neste artigo para adicionar conteúdo de um conjunto de análise para outro.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar, você precisará criar uma nova revisão configurada para adicionar os dados a.  Um novo conjunto de revisão pode ser adicionado à guia **conjuntos de revisão** da ocorrência. Para obter mais informações, consulte [criar um conjunto de revisão](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Etapa 1: identificar o conteúdo a ser adicionado a outro conjunto de revisão

Você pode adicionar conteúdo de uma análise definida para outra selecionando documentos específicos no conjunto de revisão de origem ou b seleting todos os itens retornados por consulta de conjunto de revisão.  Se você estiver adicionando itens selecionados, selecione os itens, clique em **ação**e, em seguida, clique em **Adicionar a outro conjunto de revisão**.

![Adicionar a outro conjunto de revisão](media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Etapa 2: especificar as opções para adicionar a outro conjunto de revisão

Na página **Adicionar a outro conjunto de revisão de opções** , escolha o conjunto de revisão ao qual você deseja adicionar os itens. Escolha se deseja adicionar **todos os resultados de pesquisa** ou os **itens selecionados**.  Informações adicionais fornecem opções para incluir todos os metadados dos itens e se devem ser incluídas as marcas (marcando a caixa de seleção **Rótulos** ) do conjunto de revisão de origem quando os documentos são adicionados ao novo conjunto de revisão.  

![Adicionar a outro conjunto de revisão](media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Após clicar em **OK**, um novo trabalho (chamado **adição de dados a outro conjunto de revisão**) é criado para adicionar o conteúdo a outro conjunto de revisão.  Você pode ir para a guia **trabalhos** e monitorar o progresso desse trabalho. Para obter mais informações, consulte [Manage Jobs](managing-jobs-ediscovery20.md).
