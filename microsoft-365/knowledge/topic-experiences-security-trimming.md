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
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939618"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva Topics security trimming 

Os usuários do Viva Topics não podem exibir informações em tópicos que suas permissões existentes do Office 365 os impedem de ver. Tudo o que um usuário vê em uma página de tópicos (por exemplo, sites do SharePoint, documentos, arquivos) serão informações que eles já têm permissão para ver. Os Tópicos do Viva não fazem alterações em quaisquer permissões existentes.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Por que dois usuários podem ter diferentes exibições do mesmo tópico

Quando um tópico é criado por meio da IA ou da cura manual, ele pode conter uma descrição do tópico, nomes alternativos, pessoas associadas ao tópico, bem como sites, páginas e arquivos relacionados ao tópico. Quando essas informações são exibidas em uma página de tópico, é possível que dois usuários que estão exibindo o mesmo tópico não vejam as mesmas informações.
  
Por exemplo, quando o Usuário 1 exibir a página de tópicos de Netuno, ele poderá ver essa exibição da página de tópico.

![Tópico de Netuno para o usuário 1](../media/knowledge-management/user2-topic-view.png) </br> 

No entanto, quando o Usuário 2 olha para a mesma página de tópicos de Netuno, seu modo de exibição difere do Usuário 1.  O usuário 2 pode ver o arquivo Visão geral do  produto *DG-2000* na seção Arquivos fixados e páginas da página de tópico, que não aparece para o Usuário 1. 

![Tópico de Netuno para o usuário 2](../media/knowledge-management/user1-topic-view.png) </br> 

A diferença no que os usuários podem ver no mesmo tópico é que os usuários podem não ter as permissões do Office 365 para exibir um site ou arquivo relacionado.  Os Tópicos do Viva respeitam as permissões definidas em itens em um tópico e não podem alterar o acesso a eles. No nosso exemplo, o Usuário 1 não é capaz de exibir o arquivo visão geral do *produto DG-2000* em sua página de tópicos para Netuno porque o Usuário 1 não tem permissões do Office 365 para exibir o arquivo.

Se um usuário não conseguir ver informações suficientes em um tópico para que ele seja útil, o tópico não estará disponível para o usuário. Quando isso acontecer, o usuário não verá o tópico realçado. Um usuário diferente que tenha permissões para obter mais informações no tópico para que ele seja útil, poderá ver o tópico.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Permissões de tópico para gerentes de conhecimento e colaboradores de tópicos

Os usuários que receberem permissões para gerenciar tópicos - gerentes de conhecimento - só poderão exibir informações que eles têm permissões para ver em tópicos.

Da mesma forma, os usuários que criarem e editarem permissões de tópicos - colaboradores de tópicos - só poderão exibir informações que têm permissões para ver em tópicos. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus informações de tópicos com cura manual

Os tópicos podem conter informações geradas pela IA e informações adicionadas ou editadas por colaboradores de tópicos ou gerentes de conhecimento.

 - As informações em um tópico adicionado pela AI só são visíveis para as pessoas que têm acesso ao conteúdo de origem.
 - A descrição do tópico e as informações de pessoas que foram adicionadas manualmente ou editadas por um colaborador de tópicos ou gerente de conhecimento estão visíveis para todos os que podem ver o tópico.
 - Arquivos, páginas e sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem, sejam adicionados manualmente ou adicionados pela AI.

A tabela a seguir descreve o que os usuários - visualizadores de tópicos, colaboradores e gerentes de conhecimento - podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se os usuários não têm permissões para o conteúdo de origem ou têm baixa relevância para o usuário.|
|Descrição do tópico|As descrições geradas por IA ficam visíveis apenas para usuários que têm permissões para o conteúdo de origem. As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.|
|Pessoas|As pessoas fixadas ficam visíveis para todos os usuários. As pessoas sugeridas só ficam visíveis para usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|




## <a name="see-also"></a>Confira também

