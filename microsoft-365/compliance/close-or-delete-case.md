---
title: Fechar ou excluir uma ocorrência
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
description: Saiba o que acontece quando uma investigação ou um caso legal suportado por Advanced eDiscovery caso é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657628"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Fechar ou excluir uma Advanced eDiscovery caso

Quando o caso legal ou a investigação suportado por um caso Advanced eDiscovery for concluído, você poderá fechar ou excluir um caso. Você também pode reabrir um caso fechado.

## <a name="close-a-case"></a>Fechar um caso

Veja o que acontece quando você fecha um Advanced eDiscovery caso:

- Se o caso possui qualquer local de conteúdo em retenção, essas retenções serão desativadas. Depois que a espera é desligada, um período de carência de 30 dias (chamado de *atraso)* é aplicado a locais de conteúdo que estavam em espera. Isso ajuda a impedir que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar ou recuperar conteúdo que será excluído permanentemente depois que o período de espera de atraso expirar. Para obter mais informações, consulte [Removendo locais de conteúdo de uma remoção de descoberta de eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Fechar um caso apenas fecha as retenções que estão associadas a esse caso. Se outras retenções ocorrerem em um local de conteúdo (como uma responsabilidade por litígio, uma retenção de Descoberta Principal ou uma retenção de um caso Advanced eDiscovery caso diferente), essas retenções ainda serão mantidas.

- O caso ainda está listado na página Descoberta e-descoberta no centro Microsoft 365 conformidade. Os detalhes, retenções, pesquisas e membros de uma ocorrência fechada são mantidos.

- Você pode editar uma ocorrência depois que ela for fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise em Advanced eDiscovery. A principal diferença entre caso ativo ou fechado é que as retenções são desativadas quando um caso é fechado.

Para fechar um caso:

1. Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser fechado.

2. Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.

3. Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Fechar caso**.

   ![Opção no menu Mais opções para fechar um Advanced eDiscovery caso](..\Media\CloseAdvancedeDiscoveryCase.png)

   Pode levar até 60 minutos para o processo de fechamento concluir.

## <a name="reopen-a-closed-case"></a>Reabrir um caso fechado

Quando você reabrir Advanced eDiscovery caso, quaisquer ressarcimentos que estavam no local quando o caso foi fechado não serão automaticamente reinstalados. Depois que o caso for reaberto, você terá que ir até a guia **Retém** e ativar as resvasões anteriores. Para ativar uma retenção, selecione para exibir o submenu da página e depois alterne o **Status** para **Ativo**. 

Para reabrir um caso fechado:

1. Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser reaberto.

2. Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.

3. Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Reabrir caso**.

   ![Opção no menu Mais opções para reabrir uma Advanced eDiscovery caso](..\Media\ReopenAdvancedeDiscoveryCase.png)

   Pode levar até 60 minutos para que o processo de reabertura seja concluído.

## <a name="delete-a-case"></a>Excluir uma ocorrência

Você pode excluir os casos ativos e Advanced eDiscovery fechados. Quando você exclui um caso, todos os componentes associados a ele, como lista de custodiantes, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos. O caso é removido da lista de casos na **página** Advanced eDiscovery no centro Microsoft 365 conformidade. Não é possível recuperar ou reabrir um caso excluído.

> [!NOTE]
> Em cenários de vazamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir o Advanced eDiscovery caso. Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.

Antes de poder excluir uma ocorrência (se ela está  ativa ou fechada), primeiro exclua todas as resções associadas ao caso. Isso inclui a exclusão de retém com um status de **Off**.

Para excluir ressarcições associadas a uma ocorrência:

1. Vá na **guia Retém** no Advanced eDiscovery caso que você deseja excluir.

2. Clique na espera que você deseja excluir.

3. Na página sobrevoo, clique em **Excluir bloqueio**.

Para excluir um caso:

1. Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser excluído.

2. Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.

3. Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Excluir caso**.

   ![Opção no menu Mais opções para excluir um Advanced eDiscovery caso](..\Media\DeleteAdvancedeDiscoveryCase.png)
