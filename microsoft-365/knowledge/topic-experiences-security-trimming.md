---
title: Microsoft Viva Topics security trimming
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Visão geral de como a segurança é usada para exibir tópicos.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279327"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva Topics security trimming 

Os usuários de Tópicos do Viva não podem exibir informações em tópicos que suas permissões existentes do Office 365 os impedem de ver. Tudo o que um usuário vê em uma página de tópico (por exemplo, sites do SharePoint, documentos, arquivos) será informações que ele já tem permissão para ver. O Viva Topics não faz alterações em quaisquer permissões existentes.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Por que dois usuários podem ter diferentes exibições do mesmo tópico

Quando um tópico é criado por meio de IA ou de uma correção manual, ele pode conter uma descrição do tópico, nomes alternativos, pessoas associadas ao tópico, bem como sites, páginas e arquivos relacionados ao tópico. Quando essas informações são exibidas em uma página de tópico, é possível que dois usuários que estão exibindo o mesmo tópico não vejam as mesmas informações.
  
Por exemplo, quando o Usuário 1 exibir a página de tópicos Dolm, ele poderá ver essa exibição da página de tópico.

![Tópico de Mila para o usuário 1](../media/knowledge-management/user2-topic-view.png) </br> 

No entanto, quando o Usuário 2 analisa a mesma página de tópicos do Brasil, sua exibição difere do Usuário 1.  O usuário 2 pode ver o arquivo de Visão Geral  do Produto *DG-2000* na seção Arquivos fixados e páginas da página de tópico, que não aparece para o Usuário 1. 

![Tópico de Mila para o usuário 2](../media/knowledge-management/user1-topic-view.png) </br> 

A diferença no que os usuários podem ver no mesmo tópico é que os usuários podem não ter as permissões do Office 365 para exibir um site ou arquivo relacionado.  Os Tópicos do Viva respeitam as permissões definidas nos itens de um tópico e não podem alterar o acesso a elas. No nosso exemplo, o Usuário 1 não consegue exibir o arquivo de Visão Geral do Produto *DG-2000* na página de tópicos de Mila porque o Usuário 1 não tem permissões do Office 365 para exibir o arquivo.

Se um usuário não conseguir ver informações suficientes em um tópico para que ele seja útil, o tópico não estará disponível para o usuário. Quando isso acontece, o usuário não verá o tópico realçado. Um usuário diferente que tenha permissões para obter mais informações no tópico para que ele seja útil, poderá ver o tópico.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Permissões de tópico para gerentes de conhecimento e colaboradores de tópicos

Os usuários que receberem permissões para gerenciar tópicos - gerentes de conhecimento - só poderão exibir informações que eles têm permissão para ver em tópicos.

Da mesma forma, os usuários que criaram e editaram permissões de tópico, colaboradores de tópicos, só poderão exibir as informações que têm permissão para ver nos tópicos. 


## <a name="ai-versus-manually-curated-topic-information"></a>Ia versus informações de tópicos manualmente abordados

Os tópicos podem conter informações geradas pela IA e informações adicionadas ou editadas por colaboradores de tópicos ou gerentes de conhecimento.

 - As informações em um tópico que foi adicionado pela ia só são visíveis para as pessoas que têm acesso ao conteúdo de origem.
 - A descrição do tópico e as informações de pessoas que foram adicionadas ou editadas manualmente por um colaborador de tópico ou gerente de conhecimento estão visíveis para todos que podem ver o tópico.
 - Arquivos, páginas e sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem, sejam adicionados manualmente ou adicionados pelo ia.

A tabela a seguir descreve o que os usuários ( visualizadores de tópicos, colaboradores e gerentes de conhecimento ) podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se eles têm uma baixa relevância para o usuário.|
|Descrição do tópico|As descrições geradas por IA são visíveis apenas para usuários que têm permissões para o conteúdo de origem. As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.|
|Pessoas|As pessoas fixadas ficam visíveis para todos os usuários. As pessoas sugeridas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|




## <a name="see-also"></a>Confira também

