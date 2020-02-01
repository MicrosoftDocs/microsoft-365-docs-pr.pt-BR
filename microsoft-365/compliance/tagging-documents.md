---
title: Marcar documentos em um conjunto de revisão
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
description: ''
ms.openlocfilehash: be4c86a5df7e0964744f6b5d7551382916e7ed2d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597408"
---
# <a name="tag-documents-in-a-review-set"></a>Marcar documentos em um conjunto de revisão

Organizar o conteúdo em um conjunto de revisão é importante para concluir vários fluxos de trabalho no processo de descoberta eletrônica. Isso inclui:

-  Como analisar conteúdo desnecessário

- Identificando conteúdo relevante
 
-  Identificar conteúdo que deve ser revisado por um especialista ou advogado

Quando especialistas, advogados ou outros usuários revisam o conteúdo em um conjunto de revisão, suas opiniões relacionadas ao conteúdo podem ser capturadas usando marcas. Por exemplo, se a intenção é de analisar conteúdo desnecessário, um usuário pode marcar documentos com uma marca como "não responsiva". Após o conteúdo ter sido revisado e marcado, um conjunto de análise de pesquisa pode ser criado para excluir qualquer conteúdo marcado como "não responsivo", o que elimina esse conteúdo das próximas etapas no fluxo de trabalho de descoberta eletrônica. O painel de marcas pode ser personalizado para todos os casos, para que as marcas possam suportar o fluxo de trabalho de revisão desejado.

## <a name="tag-types"></a>Tipos de marca

A descoberta eletrônica avançada fornece dois tipos de marcas:

- **Marcas de escolha única** -restringe os usuários a selecionar uma única marca dentro de um grupo. Isso pode ser útil para garantir que os usuários não selecionem marcas conflitantes, como "responsiva" e "sem resposta". 

- **Marcas de múltipla escolha** : permitir que os usuários selecionem várias marcas em um grupo.

## <a name="tag-structure"></a>Estrutura da marca

Além dos tipos de marca, a estrutura de como as marcas são organização no painel de marcas pode ser usada para tornar os documentos de marcação mais intuitivos. As marcas são agrupadas por seções. revisar definir pesquisa oferece suporte à capacidade de Pesquisar por marca e seção de marca. Isso significa que você pode criar uma análise definir pesquisa para recuperar documentos marcados com qualquer marca em uma seção.

![Seções de marcas no painel de marcas](media/Tagtypes.png)

As marcas podem ser organizadas com o aninhamento de uma seção. Por exemplo, se a intenção é identificar e marcar conteúdo privilegiado, o aninhamento pode ser usado para tornar claro que um usuário pode marcar um documento como "privilegiado" e selecionar o tipo de privilégio, verificando a marca aninhada apropriada.

![Marcas aninhadas em uma seção tag](media/Nestingtags.png)

## <a name="applying-tags"></a>Aplicando marcas

Há várias maneiras de aplicar uma marca ao conteúdo.

### <a name="tagging-a-single-document"></a>Marcando um único documento

Ao exibir um documento em um conjunto de revisão, você pode exibir as marcas que uma revisão pode usar clicando em **painel de codificação**.

![Clique no painel de marcas para exibir o painel de marcas](media/Singledoctag.png)

Isso permitirá que você aplique marcas ao documento exibido no visualizador.

### <a name="bulk-tagging"></a>Marcação em massa

A marcação em massa pode ser feita selecionando vários arquivos na grade de resultados e, em seguida, usando as marcas no **painel de codificação** , semelhante a marcação de documentos únicos. A desmarcação em massa pode ser feita selecionando marcas duas vezes; o primeiro clique irá aplicar a marca e a segunda será garantir que a marca seja desmarcada para todos os arquivos selecionados.

![Uma captura de tela de uma descrição de telefone de célula gerada automaticamente](media/Bulktag.png)

> [!NOTE]
> Quando a marcação em massa, o painel de marcação exibirá uma contagem de arquivos que estão marcados para cada marca no painel.

### <a name="tagging-in-other-review-panels"></a>Marcação em outros painéis de revisão

Ao revisar documentos, você pode usar os outros painéis de revisão para examinar outras características de documentos na grade de resultados. Isso inclui a revisão de outros documentos relacionados, segmentos de email, duplicatas próximas e hash duplicados. Por exemplo, ao revisar documentos relacionados (usando o painel de revisão **da família de documentos** ), você pode reduzir significativamente o tempo de análise ao marcar documentos relacionados em massa. Por exemplo, se uma mensagem de email tiver vários anexos e você quiser garantir que toda a família seja marcada de forma consistente.

Por exemplo, veja como exibir o painel de **codificação** ao usar o documento painel revisão **da família** :

1. Com o painel de revisão aberto para um documento selecionado (por exemplo, exibindo a lista de conteúdo relacionado no painel de revisão **da família de documentos** , clique em **documentos de código** na parte superior do painel de revisão atual.

   O painel de codificação é exibido é uma janela pop-up.

2. Escolha uma ou mais marcas para aplicar o documento selecionado. 

3. Para marcar todos os documentos, selecione todos os documentos no painel **família** de documentos, clique em **documentos de código**e escolha as marcas a serem aplicadas a toda a família de documentos.

![Uma captura de tela de uma descrição de postagem de mídia social gerada automaticamente](media/Relatedtag.png)
