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
description: Saiba o que acontece quando uma investigação ou um caso jurídico suportado por um caso de descoberta eletrônica avançada é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292407"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Fechar ou excluir uma ocorrência de descoberta eletrônica avançada

Quando o caso ou investigação legal suportado por uma ocorrência de descoberta eletrônica avançada estiver concluído, você poderá fechar ou excluir uma ocorrência. Você também pode reabrir uma ocorrência fechada.

## <a name="close-a-case"></a>Fechar uma ocorrência

Veja o que acontece quando você fecha uma caixa de descoberta eletrônica avançada:

- Se o caso contiver qualquer local de conteúdo em espera, essas isenções serão desativadas. Isso pode resultar na exclusão ou limpeza permanente do conteúdo, seja pelo usuário ou por um processo automatizado, como uma política de exclusão.

- O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso. Se outras isenções forem mantidas em um local de conteúdo (como uma retenção de litígio, controle de descoberta eletrônica principal ou uma retenção de uma ocorrência de descoberta eletrônica avançada diferente), elas ainda serão mantidas.

- O caso ainda está listado na página descoberta eletrônica no centro de conformidade do Microsoft 365. Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.

- Você pode editar uma ocorrência após ela ser fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise na descoberta eletrônica avançada. A principal diferença entre casos ativos e fechados é que a retenção é desativada quando um caso é fechado.

Para fechar uma ocorrência:

1. Na página **descoberta eletrônica avançada** , selecione o caso que você deseja fechar.

2. Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.

3. Clique em **fechar caso**.

   Pode levar até 60 minutos para que o processo de fechamento seja concluído.

## <a name="reopen-a-closed-case"></a>Reabrir uma ocorrência fechada

Quando você reabre um caso de descoberta eletrônica avançada, qualquer bloqueio que estava no lugar quando o caso foi fechado não será restabelecido automaticamente. Depois que o caso for reaberto, você terá que ir para a guia **isenções** e ativar as isenções anteriores. Para ativar uma retenção, selecione-a para exibir a página do submenu e, em seguida, defina o **status** de alternância como **ativado**.

Para reabrir uma ocorrência fechada:

1. Na página **descoberta eletrônica avançada** , selecione o caso que você deseja excluir.

2. Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.

3. Clique em **reabrir caso**.

   Pode levar até 60 minutos para que o processo de reabertura seja concluído.

## <a name="delete-a-case"></a>Excluir uma ocorrência

Você pode excluir casos de descoberta eletrônica avançados ativos e fechados. Quando você exclui um caso, todos os componentes associados ao caso, como a lista de responsáveis, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos. O caso é removido da lista de casos na página **descoberta eletrônica avançada** no centro de conformidade da Microsoft 365. Não é possível recuperar ou reabrir um caso excluído.

> [!NOTE]
> Em cenários de derramamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir a caixa de descoberta eletrônica avançada. Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.

Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* isenções associadas à ocorrência. Isso inclui a exclusão de isenções com o status **desativado**.

Para excluir suspensões associadas a um caso:

1. Vá para a guia **isenções** na caixa de descoberta eletrônica avançada que você deseja excluir.

2. Clique na isenção que você deseja excluir.

3. Na página do menu suspenso, clique em **excluir isenção**.

Para excluir uma ocorrência:

1. Na página **descoberta eletrônica avançada** , selecione o caso que você deseja excluir.

2. Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.

3. Clique em **excluir caso**.
