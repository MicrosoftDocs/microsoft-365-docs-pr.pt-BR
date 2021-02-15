---
title: Indexação de dados custodiante avançados
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
description: Quando um custodiante é adicionado a uma ocorrência de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750752"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indexação de dados custodiante avançados

Quando um custodiante é adicionado a uma ocorrência de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.  Esse processo é chamado *de indexação avançada.* O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivo sem suporte ou quando são encontrados limites de tamanho de arquivo de indexação.

Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:

- [Tipos de arquivo com suporte na Descoberta Avançada](supported-filetypes-ediscovery20.md)

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de arquivo indexados pela pesquisa do Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Exibindo resultados de indexação avançada

Depois que o processo de indexação Avançada for concluído, você poderá obter uma compreensão da eficácia do reprocessamento.  No modo de exibição de resultados de indexação Avançada na guia **Processamento** de um caso, o gráfico lista o número de itens adicionados ao *índice híbrido.*  O índice híbrido é onde a Descoberta Avançada armazena o conteúdo reprocessado.

Essa exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo. Para saber mais, confira:

- [Correção de erros durante o processamento de dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Correção de erros de item único](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Atualizando o índice Avançado para custodiantes

Quando um custodiante é adicionado a uma ocorrência de Descoberta Avançada, todos os itens parcialmente indexados são reprocessados. No entanto, conforme o tempo passa, itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou à conta do OneDrive.  Se necessário, você pode atualizar o índice para um custodiante específico. Para obter mais informações, [consulte Gerenciar custodiantes em um caso de Descoberta Avançada.](manage-new-custodians.md#re-index-custodian-data) Você também pode atualizar o índice de todos os custodiantes em um caso clicando no índice Atualizar **na** guia **Processamento.**

> [!NOTE]
> A atualização de índices custodiante é um processo de longa execução. É recomendável que você não atualize índices mais de uma vez por dia em um caso.
