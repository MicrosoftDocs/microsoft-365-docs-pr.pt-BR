---
title: Fechar, reabrir e excluir casos de descoberta eletrônica principais
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
description: Este artigo descreve como gerenciar as principais ocorrências de descoberta eletrônica. Isso inclui fechar uma ocorrência, reabrir uma ocorrência fechada e excluir uma ocorrência.
ms.openlocfilehash: 45282486c2c3b1d00b99a1cda5968b3bb042f6c2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208413"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Fechar, reabrir e excluir uma ocorrência de descoberta eletrônica principal

Este artigo descreve como fechar, reabrir e excluir casos de descoberta eletrônica principais no Microsoft 365.

## <a name="close-a-case"></a>Fechar uma ocorrência

Quando o caso ou investigação legal suportado por uma caixa de descoberta eletrônica principal é concluída, você pode fechar o caso. Veja o que acontece quando você fecha um caso:
  
- Se o caso contiver qualquer local de conteúdo em retenção de descoberta eletrônica, essas isenções serão desativadas. Isso pode resultar na exclusão ou limpeza permanente do conteúdo, seja pelo usuário ou por um processo automatizado, como uma política de exclusão.

- O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso. Se outras isenções forem colocadas em um local de conteúdo (como uma retenção de litígio, uma política de retenção ou uma retenção de um caso de descoberta eletrônica diferente), essas isenções ainda serão mantidas.

- O caso ainda está listado na página de descoberta eletrônica principal no centro de conformidade da Microsoft 365. Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.

- Você pode editar uma ocorrência após ela ser fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa. A principal diferença entre casos ativos e fechados é que a descoberta eletrônica é desativada quando um caso é fechado.

Para fechar uma ocorrência:
  
1. No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.

2. Clique no nome do caso que você deseja fechar.

    A página **gerenciar esse** submenu de caso é exibida.

3. Em **gerenciar o status de caso**, clique em **fechar caso**.

    Um aviso é exibido dizendo que as suspensões associadas ao caso serão desativadas.

4. Clique em **Sim** para fechar o caso.

    O status da página **gerenciar esse** submenu de caso é alterado de **ativo** para **encerramento**.

5. Feche a página **gerenciar este caso** .

6. Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status da ocorrência fechada. Pode levar até 60 minutos para que o processo de fechamento seja concluído.

    Quando o processo estiver concluído, o status da ocorrência será alterado para **fechado** na página de **descoberta eletrônica principal** . Clique no nome do caso novamente para exibir a página **gerenciar este caso** , que contém informações sobre quando o caso foi fechado e quem o fechou.

## <a name="reopen-a-closed-case"></a>Reabrir uma ocorrência fechada

Quando você reabrir um caso, qualquer bloqueio de descoberta eletrônica que estava no lugar quando o caso foi fechado não será restabelecido automaticamente. Depois que o caso for reaberto, você terá que ir para a página de **isenções** e ativar as isenções anteriores. Para ativar uma retenção, selecione-a para exibir a página do submenu e, em seguida, defina o **status** de alternância como **ativado**.
  
1. No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.

2. Clique no nome do caso que você deseja reabrir.

    A página **gerenciar esse** submenu de caso é exibida. 

3. Em **gerenciar o status de caso**, clique em **reabrir caso**.

    Um aviso é exibido dizendo que as suspensões que estavam associadas ao caso em que foram fechadas não serão ativadas automaticamente.

4. Clique em **Sim** para reabrir a ocorrência.

    O status da página **gerenciar esse** submenu de caso é alterado de **fechado** para **ativo**.

5. Feche a página **gerenciar este caso** . 

6. Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status do caso reaberto. Pode levar até 60 minutos para que o processo de reabertura seja concluído. 

    Quando o processo estiver concluído, o status da ocorrência será alterado para **ativo** na página de **descoberta eletrônica principal** . 
  
## <a name="delete-a-case"></a>Excluir uma ocorrência

Você também pode excluir casos de descoberta eletrônica ativos e fechados. Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas e o caso é removido da lista de casos na página de **descoberta eletrônica principal** do centro de conformidade da Microsoft 365. Não é possível reabrir um caso excluído.

Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* retenções de descoberta eletrônica associadas à ocorrência. Isso inclui a exclusão de isenções com o status **desativado**. 

Para excluir uma retenção de descoberta eletrônica:

1. Vá para a guia **isenções** , caso você queira excluir.

2. Clique na isenção que você deseja excluir.

3. Na página do menu suspenso, clique em **excluir isenção**.

Para excluir uma ocorrência:

1. No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.

2. Clique no nome do caso que você deseja excluir.

3. Em **gerenciar status de caso** na página de submenu, clique em **excluir caso**.

Se o caso que você está tentando excluir ainda contiver bloqueios de descoberta eletrônica, você receberá uma mensagem de erro. Você terá que excluir todas as suspensões associadas à ocorrência e, em seguida, tentar excluir a ocorrência novamente.
