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
description: Quando um custodiante é adicionado a um caso de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911205"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indexação de dados custodiante avançados

Quando um custodiante é adicionado a um caso de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.  Esse processo é chamado *de indexação avançada*. O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivo sem suporte ou quando os limites de tamanho do arquivo de indexação são encontrados.

Para saber mais sobre o suporte ao processamento e itens parcialmente indexados, consulte:

- [Tipos de arquivo com suporte na Descoberta Avançada da Descoberta](supported-filetypes-ediscovery20.md)

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de arquivo indexados pela pesquisa do Exchange](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Exibindo resultados avançados de indexação

Depois que o processo de indexação avançada for concluído, você poderá obter uma compreensão da eficácia do reprocessamento.  No modo de exibição De resultados de indexação avançada na guia **Processamento** de uma ocorrência, o gráfico lista o número de itens adicionados ao *índice híbrido*.  O índice híbrido é onde a Descoberta Virtual Avançada armazena o conteúdo reprocessado.

Essa exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo. Para mais informações, confira:

- [Correção de erros durante o processamento de dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Correção de erros de item único](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Atualizando o índice avançado para custodiantes

Quando um custodiante é adicionado a um caso de Descoberta Avançada, todos os itens parcialmente indexados são reprocessados. No entanto, com o passar do tempo, itens indexados mais parcialmente podem ser adicionados à caixa de correio de um usuário ou à conta do OneDrive.  Se necessário, você pode atualizar o índice para o custodiante específico. Para obter mais informações, consulte [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data). Você também pode atualizar o índice para todos os custodiantes em um caso clicando no índice **Atualizar** na guia **Processamento.**

> [!NOTE]
> A atualização dos índices de custodiante é um processo em execução longa. É recomendável que você não atualize índices mais de uma vez por dia em um caso.