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
description: Quando um Objecté adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo no Office 365 que foi considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 3c1bead5f853a39410a6a018f170ee637dfcf84e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072888"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indexação de dados custodiante avançados

Quando um Objecté adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo no Office 365 que foi considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.  Esse processo é chamado de *indexação avançada*. O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.

Para saber mais sobre o processamento de suporte no Office 365 e itens parcialmente indexados, consulte:

- [Tipos de arquivo com suporte na descoberta eletrônica avançada](supported-filetypes-ediscovery20.md)

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de arquivo indexados pela pesquisa do Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Exibindo resultados avançados de indexação

Após a conclusão do processo de indexação avançada, você pode entender a eficácia da reprocessamento.  No modo de exibição de resultados de indexação avançados na guia **processamento** para um caso, o gráfico lista o número de itens adicionados ao *índice híbrido*.  O índice híbrido é onde a descoberta eletrônica avançada armazena o conteúdo reprocessado.

Este modo de exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo. Para saber mais, veja:

- [Correção de erros durante o processamento de dados](error-remediation.md)

- [Correção de erros de item único](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Atualizando o índice avançado para os responsáveis

Quando um responsáveis é adicionado a uma caixa de descoberta eletrônica avançada, todos os itens parcialmente indexados são reprocessados. No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.  Se necessário, você pode atualizar o índice para os responsáveis específicos. Para obter mais informações, consulte [Manage responsáveis em uma caixa de descoberta eletrônica avançada](manage-new-custodians.md#re-index-custodian-data). Você também pode atualizar o índice para todos os responsáveis em um caso clicando no **índice de atualização** na guia **processamento** .

> [!NOTE]
> Atualizar os índices dos responsáveis é um processo de execução longa. É recomendável que você não atualize os índices mais de uma vez por dia em um caso.
