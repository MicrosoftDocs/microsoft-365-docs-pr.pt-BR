---
title: Fechar, reabrir e excluir principais casos de Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como gerenciar os principais casos de Descoberta eDiscovery. Isso inclui fechar um caso, reabrir um caso fechado e excluir um caso.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684094"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Fechar, reabrir e excluir um caso de Descoberta Principal

Este artigo descreve como fechar, reabrir e excluir os principais casos de Descoberta Microsoft 365.

## <a name="close-a-case"></a>Fechar um caso

Quando o caso legal ou a investigação com suporte de um caso core de Descoberta eDiscovery for concluído, você poderá fechar o caso. Veja o que acontece quando você fecha um caso:
  
- Se o caso contiver qualquer ressarção de Descoberta E, eles serão desligados. Depois que a espera é desligada, um período de carência de 30 dias (chamado de *atraso)* é aplicado a locais de conteúdo que estavam em espera. Isso ajuda a impedir que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar e restaurar conteúdo antes que ele possa ser excluído permanentemente depois que o período de espera de atraso expirar. Para obter mais informações, consulte [Removendo locais de conteúdo de uma remoção de descoberta de eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Fechar um caso apenas fecha as retenções que estão associadas a esse caso. Se outras retenções são colocadas em um local de conteúdo (como uma Retenção de Litígio, uma política de retenção ou uma retenção de um caso de Descoberta eDiscovery Principal diferente), essas retenções ainda serão mantidas.

- O caso ainda está listado na página Descoberta Principal da Descoberta Microsoft 365 de conformidade. Os detalhes, retenções, pesquisas e membros de uma ocorrência fechada são mantidos.

- Você pode editar uma ocorrência depois que ela for fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa. A principal diferença entre os casos ativos e fechados é que os ressarcedores de Descoberta e São desligados quando um caso é fechado.

Para fechar um caso:
  
1. No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.

2. Clique no nome do caso que você deseja fechar.

   ![Fechar caso na home page do caso](../media/eDiscoveryCaseHomePage.png)

3. Na home page, em **Status**, clique **em Fechar caso**.

    Um aviso é exibido dizendo que os ressarcições associados à ocorrência serão desligados.

4. Clique **em Sim** para fechar o caso.

    O status na home page do caso é alterado de **Ativo** para **Fechamento**.

5. Na página **Descoberta Automática Principal,** clique em **Atualizar** para atualizar o status do caso fechado. Pode levar até 60 minutos para o processo de fechamento concluir.

    Quando o processo é concluído, o status da ocorrência é alterado para **Fechado** na página **Descoberta Principal.**

## <a name="reopen-a-closed-case"></a>Reabrir um caso fechado

Quando você reabrir um caso, qualquer Descoberta Automática que estava no local quando o caso foi fechado não será automaticamente restabelecido. Depois que o caso for reaberto, você terá que ir para a página **Retém** e ativar as ressarções anteriores. Para ativar uma retenção, selecione para exibir o submenu da página e depois alterne o **Status** para **Ativo**. 
  
1. No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.

2. Clique no nome do caso que você deseja reabrir.

   ![Reabrir um caso fechado](../media/eDiscoveryCaseHomePageReopen.png)

3. Na home page, em **Status**, clique em **Reabrir caso**.

    Um aviso é exibido dizendo que as resvações associadas à ocorrência quando ela foi fechada não serão ativados automaticamente.

4. Clique **em Sim** para reabrir o caso.

    O status na página de sobrevoo da home page de caso é alterado **de Closed** para **Active**.

5. Na página **Descoberta Principal da Descoberta Automática,** clique em **Atualizar** para atualizar o status do caso reaberto. Pode levar até 60 minutos para que o processo de reabertura seja concluído. 

    Quando o processo é concluído, o status da ocorrência é alterado para **Ativo** na página **Descoberta Principal.**

6. (Opcional) Para ativar quaisquer bloqueios associados ao caso  reaberto, vá para a guia Bloqueios, selecione uma responsabilidade e selecione a caixa de seleção em **Status** na página de subsuletor de espera.
  
## <a name="delete-a-case"></a>Excluir uma ocorrência

Você também pode excluir casos ativos e fechados de Descoberta eDiscovery Principal. Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas, e o caso é removido da lista de casos na página Descoberta Principal de **Descoberta** e No centro de conformidade do Microsoft 365. Não é possível reabrir um caso excluído.

Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), primeiro exclua todas as resções de *Descoberta* De eDiscovery associadas ao caso. Isso inclui a exclusão de retém com um status de **Off**. 

Para excluir uma ressarção de Descoberta e:

1. Vá para a guia **Retém** no caso de você querer excluir.

2. Selecione a espera que você deseja excluir.

3. Na página de sobrevoo, clique em **Excluir**.

      ![Excluir uma responsabilidade de Descoberta De eDiscovery](../media/DeleteeDiscoveryHold.png)

Para excluir um caso:

1. No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.

2. Clique no nome do caso que você deseja excluir.

3. Na home page do caso, em **Status**, clique **em Excluir caso**.

      ![Excluir uma ocorrência](../media/eDiscoveryCaseHomePageDelete.png)

Se o caso que você estiver tentando excluir ainda contiver retém a Descoberta E, você receberá uma mensagem de erro. Você terá que excluir todas as ressarcições associadas à ocorrência e tentar novamente excluir o caso.
