---
title: Marcar documentos em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Marcar documentos em um conjunto de revisão ajuda a remover conteúdo desnecessário e identificar conteúdo relevante em um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736236"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Marcar documentos em um conjunto de revisão em Advanced eDiscovery

Organizar conteúdo em um conjunto de revisão é importante para concluir vários fluxos de trabalho no processo de Descoberta Eletrônico. Isso inclui:

- Selecionando conteúdo desnecessário

- Identificar conteúdo relevante

- Identificar conteúdo que deve ser revisado por um especialista ou advogado

Quando especialistas, advogados ou outros usuários revisam conteúdo em um conjunto de revisão, suas opiniões relacionadas ao conteúdo podem ser capturadas usando marcas. Por exemplo, se a intenção for eliminar conteúdo desnecessário, um usuário poderá marcar documentos com uma marca como "não responsiva". Depois que o conteúdo é revisado e marcado, uma pesquisa de conjunto de revisão pode ser criada para excluir qualquer conteúdo marcado como "não responsivo". Esse processo elimina o conteúdo não responsivo das próximas etapas no fluxo de trabalho de Descoberta Eletrônico. O painel de marcação em um conjunto de revisão pode ser personalizado para cada caso para que as marcas suportem o fluxo de trabalho de revisão pretendido para o caso.

> [!NOTE]
> O escopo das marcas é Advanced eDiscovery caso. Isso significa que um caso só pode ter um conjunto de marcas que os revisadores podem usar para marcar documentos de conjunto de revisão. Não é possível configurar um conjunto diferente de marcas para uso em conjuntos de revisão diferentes no mesmo caso.

## <a name="tag-types"></a>Tipos de marca

Advanced eDiscovery fornece dois tipos de marcas:

- **Marcas de opção única**: Restringe os revisadores a selecionar uma única marca dentro de um grupo. Esses tipos de marcas podem ser úteis para garantir que os revisadores não selecionem marcas conflitantes, como "responsiva" e "não responsiva". Marcas de opção única aparecem como botões de opção.

- **Marcas de várias opções**: Permitir que as avaliações selecionem várias marcas em um grupo. Esses tipos de marcas aparecem como caixas de seleção.

## <a name="tag-structure"></a>Estrutura de marca

Além dos tipos de marca, a estrutura de como as marcas são organizadas no painel de marcas pode ser usada para tornar a marcação de documentos mais intuitiva. As marcas são agrupadas por seções. A pesquisa de conjunto de revisão dá suporte à capacidade de pesquisar por marca e por seção de marca. Isso significa que você pode criar uma pesquisa de conjunto de revisão para recuperar documentos marcados com qualquer marca em uma seção.

![Seções de marca no painel de marca](../media/TagTypes.png)

Você pode organizar ainda mais as marcas aninhando-as em uma seção. Por exemplo, se a intenção for identificar e marcar conteúdo privilegiado, o aninhamento pode ser usado para deixar claro que um revistor pode marcar um documento como "Privileged" e selecionar o tipo de privilégio verificando a marca aninhada apropriada.

![Marcas aninhadas em uma seção de marca](../media/NestingTags.png)

## <a name="create-tags"></a>Criar marcas

Antes de aplicar marcas a documentos no conjunto de revisão, você precisa criar uma estrutura de marca.

1. Abra um conjunto de revisão e navegue até a barra de comandos e selecione **Marcar por consulta**.

2. No painel de marcação, selecione **Gerenciar opções de marca**

3. Selecione **Adicionar seção de marca**.

4. Digite um título de grupo de marca e uma descrição opcional e clique em **Salvar**.

5. Selecione o menu suspenso ponto triplo ao lado do título do grupo de marca e clique em **Adicionar** caixa de seleção ou **no botão Adicionar opção**.

6. Digite um nome e uma descrição para a caixa de seleção ou botão de opção.

7. Repita esse processo para criar novas seções de marca, opções de marca e caixas de seleção.

   ![Configurar estrutura de marca](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a>Aplicando marcas

Com a estrutura de marca no local, os revisadores podem aplicar marcas a documentos em um conjunto de revisão. Há duas maneiras diferentes de aplicar marcas:

- Arquivos de marca

- Marca por consulta

### <a name="tag-files"></a>Arquivos de marca

Se você selecionar um único item ou vários itens em um conjunto de revisão, poderá aplicar marcas à seleção deles clicando em **Arquivos de** marca na barra de comandos. No painel de marcação, você pode selecionar uma marca e ela é aplicada automaticamente aos documentos selecionados.

![Marcar arquivos selecionados](../media/TagFile2.png)

> [!NOTE]
> As marcas serão aplicadas somente a itens selecionados na lista de itens.

### <a name="tag-by-query"></a>Marca por consulta

A marcação por consulta permite que você aplique marcas a todos os itens exibidos por uma consulta de filtro aplicada no momento no conjunto de revisão.

1. Desmarque todos os itens no conjunto de revisão e vá para a barra de comandos e selecione **Marcar por consulta**.

2. No painel de marcação, selecione a marca que você deseja aplicar.

3. Na lista **suspenso Seleção de** marca, há três opções que determinam a quais itens aplicar a marca.

   - **Itens que corresponderem à consulta aplicada**: aplica marcas a itens específicos que corresponderem às condições de consulta do filtro.

   - **Inclua itens da família associados**: Aplica marcas a itens específicos que corresponderem às condições de consulta do filtro e seus itens de família associados. *Itens da* família são itens que compartilham o mesmo valor de metadados FamilyId.  

   - **Inclua itens de conversa associados:** aplica marcas a itens que corresponderem às condições de consulta do filtro e seus itens de conversa associados. *Os itens de* conversa são itens que compartilham os mesmos valores de metadados ConversationId.

   ![Seleção de marca](../media/TagByQuery2.png)

4. Clique **em Iniciar o trabalho de marcação** para disparar o trabalho de marcação.

## <a name="tag-filter"></a>Filtro de marca

Use o filtro de marca no conjunto de revisão para encontrar ou excluir rapidamente itens dos resultados da consulta com base em como um item é marcado. 

1. Selecione **Filtros** para expandir o painel de filtro.

2. Selecione e **expanda propriedades de item**.

3. Role para baixo para encontrar o filtro chamado **Tag,** selecione a caixa de seleção e clique em **Feito**.

4. Para incluir ou excluir itens com uma marca específica de uma consulta, faça um dos seguintes:

   - **Incluir itens**: selecione o valor da marca e selecione **Igual a qualquer um** no menu suspenso.

      Ou

   - **Excluir itens**: selecione o valor da marca e selecione Igual a **nenhum no** menu suspenso.

     ![Itens de exclusão de filtro de marca](../media/TagFilterExclude.png)

> [!NOTE]
> Certifique-se de atualizar a página para garantir que o filtro de marca exibe as alterações mais recentes na estrutura de marca.
