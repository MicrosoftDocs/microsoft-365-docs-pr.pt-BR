---
title: Indexação avançada de dados para uma investigação
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
description: Saiba como usar a indexação avançada para garantir que sua pesquisa Capture todos os dados que você deseja investigar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285957"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Indexação avançada de dados para uma investigação

O conteúdo no sistema ativo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação. Ao lidar com o despejo de dados de alto risco, você deseja garantir que sua pesquisa tenha capturado todos os dados que você deseja investigar. Quando uma pessoa de interesse é adicionada a uma investigação de dados, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável. Esse processo é chamado de *indexação avançada*. 

Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:

- [Tipos de arquivo com suporte em investigações de dados](supported-filetypes-datainvestigations.md)

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de arquivo indexados pela pesquisa do Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Exibindo resultados avançados de indexação

Após a conclusão do processo de indexação avançada, você pode entender a eficácia do reprocessamento.  Na exibição de indexação de pessoas de interesse, o gráfico lista todos os itens adicionados ao *índice híbrido*.  O índice híbrido é onde as investigações de dados (prévia) armazenam o conteúdo reprocessado.

O gráfico também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo. Para obter mais informações, consulte [Error remediation When Processing data](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Atualizando índices avançados para pessoas de interesse

Quando uma pessoa de interesse é adicionada a uma investigação de dados, todos os itens parcialmente indexados são reprocessados. No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.  Quando necessário, você pode atualizar os índices.

> [!NOTE]
> A atualização de pessoas de índices de interesse é um processo de execução demorada. É recomendável que você não atualize os índices mais de uma vez por dia em uma investigação.
