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
description: Quando um qualificador é adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750752"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indexação de dados custodiante avançados

Quando um qualificador é adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.  Esse processo é chamado de *indexação avançada*. O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.

Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:

- [Tipos de arquivo com suporte na descoberta eletrônica avançada](supported-filetypes-ediscovery20.md)

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de arquivo indexados pela pesquisa do Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Exibindo resultados avançados de indexação

Após a conclusão do processo de indexação avançada, você pode entender a eficácia do reprocessamento.  No modo de exibição de resultados de indexação avançados na guia **processamento** para um caso, o gráfico lista o número de itens adicionados ao *índice híbrido*.  O índice híbrido é onde a descoberta eletrônica avançada armazena o conteúdo reprocessado.

Este modo de exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo. Para saber mais, confira:

- [Correção de erros durante o processamento de dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Correção de erros de item único](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Atualizando o índice avançado para os responsáveis

Quando um responsáveis é adicionado a uma caixa de descoberta eletrônica avançada, todos os itens parcialmente indexados são reprocessados. No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.  Se necessário, você pode atualizar o índice para os responsáveis específicos. Para obter mais informações, consulte [Manage responsáveis em uma caixa de descoberta eletrônica avançada](manage-new-custodians.md#re-index-custodian-data). Você também pode atualizar o índice para todos os responsáveis em um caso clicando no **índice de atualização** na guia **processamento** .

> [!NOTE]
> Atualizar os índices dos responsáveis é um processo de execução longa. É recomendável que você não atualize os índices mais de uma vez por dia em um caso.
