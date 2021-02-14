---
title: Fechar, reabrir e excluir ocorrências de Descobertas Principais
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
description: Este artigo descreve como gerenciar casos principais de Descobertas eDiscovery. Isso inclui fechar uma ocorrência, reabrir uma ocorrência fechada e excluir uma ocorrência.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412790"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Fechar, reabrir e excluir um caso principal de Descoberta eDiscovery

Este artigo descreve como fechar, reabrir e excluir ocorrências de Descobertas Principais no Microsoft 365.

## <a name="close-a-case"></a>Fechar uma ocorrência

Quando o caso jurídico ou a investigação com suporte em um caso de Descoberta e Principal for concluído, você poderá fechar o caso. Veja o que acontece quando você fecha um caso:
  
- Se a ocorrência contiver qualquer local de conteúdo em espera de Descoberta eDiscovery, essas regiões serão desligadas. Depois que a espera é desligada, um período de carência de 30 dias (chamado de espera de *atraso)* é aplicado a locais de conteúdo que estavam em espera. Isso ajuda a evitar que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar e restaurar conteúdo antes que ele possa ser excluído permanentemente após o período de espera de atraso expirar. Para obter mais informações, [consulte Removendo locais de conteúdo de um eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Fechar uma ocorrência só desliga as retém associadas a esse caso. Se outras retenções são colocadas em um local de conteúdo (como uma Retenção de Litígio, uma política de retenção ou uma retenção de um caso de Descoberta eDiscovery Principal diferente), essas retenções ainda serão mantidas.

- O caso ainda está listado na página Descoberta e Principal no centro de conformidade do Microsoft 365. Os detalhes, retidos, pesquisas e membros de um caso fechado são mantidos.

- Você pode editar uma ocorrência depois que ela for fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa. A principal diferença entre os casos ativos e fechados é que as isenções de Descoberta eDiscovery são desligadas quando um caso é fechado.

Para fechar um caso:
  
1. No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.

2. Clique no nome da ocorrência que você deseja fechar.

    A **página Gerenciar esse caso** é exibida.

3. Em **Gerenciar status da ocorrência,** clique em Fechar **caso.**

    Um aviso é exibido dizendo que as iseções associadas à ocorrência serão desligadas.

4. Clique **em Sim** para fechar a ocorrência.

    O status na página **Gerenciar este caso** do flyout é alterado de **Ativo** para **Fechamento.**

5. Feche a **página Gerenciar este caso.**

6. Na página **Descoberta Automática Principal,** clique em Atualizar para atualizar o status do caso fechado.  Pode levar até 60 minutos para que o processo de fechamento seja concluído.

    Quando o processo é concluído, o status da ocorrência é alterado para **Fechado** na página **Descoberta Principal.** Clique no nome da ocorrência  novamente para exibir a página gerenciar esse caso do flyout, que contém informações sobre quando o caso foi fechado e quem o fechou.

## <a name="reopen-a-closed-case"></a>Reabrir um caso fechado

Quando você reabrir um caso, qualquer resuspensão de Descoberta Automática que estava no local quando o caso foi fechado não será automaticamente restabelecimento. Depois que o caso for reaberto, você terá que ir para a página **Isões** e ativar as retém anteriores. Para ativar uma espera, selecione-a para exibir a página do flyout e, em seguida, de definir a **alternância de Status** para **Ativar.**
  
1. No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.

2. Clique no nome do caso que você deseja reabrir.

    A **página Gerenciar esse caso** é exibida. 

3. Em **Gerenciar status do caso,** clique em **Reabrir caso.**

    Um aviso é exibido dizendo que as resuspensão que estavam associadas à ocorrência quando ele foi fechado não serão ativados automaticamente.

4. Clique **em Sim** para reabrir o caso.

    O status na página **Gerenciar este caso** do flyout é alterado de **Fechado** para **Ativo.**

5. Feche a **página Gerenciar este caso.** 

6. Na página **Descoberta Automática** Principal,  clique em Atualizar para atualizar o status do caso reaberto. Pode levar até 60 minutos para que o processo de reabertura seja concluído. 

    Quando o processo é concluído, o status da ocorrência é alterado para **Ativo** na página **Descoberta Principal.** 
  
## <a name="delete-a-case"></a>Excluir uma ocorrência

Você também pode excluir ocorrências de Descobertas Principais ativas e fechadas. Quando você exclui uma ocorrência, todas as pesquisas e exportações no caso são excluídas, e o caso é removido da lista de ocorrências na página **Descoberta** Principal do Centro de conformidade do Microsoft 365. Não é possível reabrir um caso excluído.

Antes de excluir uma ocorrência (se ela está ativa  ou fechada), primeiro você deve excluir todas as retém de Descobertas De eDiscovery associadas à ocorrência. Isso inclui a exclusão de retém com um status **de Desligado**. 

Para excluir um eDiscovery hold:

1. Vá para **a guia** Retém no caso em que você deseja excluir.

2. Clique na espera que você deseja excluir.

3. Na página do flyout, clique em **Excluir bloqueio.**

Para excluir uma ocorrência:

1. No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.

2. Clique no nome da ocorrência que você deseja excluir.

3. Em **Gerenciar status da ocorrência** na página do sub-sub-piloto, clique em Excluir **caso.**

Se o caso que você estiver tentando excluir ainda contiver rescuções de Descoberta eDiscovery, você receberá uma mensagem de erro. Você terá que excluir todas as retém associadas à ocorrência e, em seguida, tentar novamente excluir a ocorrência.
