---
title: Tópico experiências de filtragem de segurança (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Visão geral de como a segurança é usada para exibir tópicos.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698782"
---
# <a name="topic-experiences-security-trimming-preview"></a>Tópico experiências de filtragem de segurança (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).

Tópico experiências os usuários não poderão exibir informações nos tópicos que suas permissões existentes do Office 365 impedem que eles vejam. Tudo o que um usuário vê em uma página de tópico (por exemplo, sites do SharePoint, documentos, arquivos) serão informações que eles já podem ver. As experiências de tópico não fazem alterações nas permissões existentes.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Por que dois usuários podem ter modos de exibição diferentes do mesmo tópico

Quando um tópico é criado através do AI ou da seção de manual, ele pode conter uma descrição do tópico, nomes alternativos, pessoas associadas ao tópico, bem como sites, páginas e arquivos relacionados ao tópico. Quando essas informações são exibidas em uma página de tópico, é possível que dois usuários que estejam exibindo o mesmo tópico não vejam as mesmas informações.
  
Por exemplo, quando o usuário 1 exibe a página de tópico Neptune, isso é o que eles podem ver.

![Tópico Neptune para o usuário 1](../media/knowledge-management/user2-topic-view.png) </br> 

No entanto, quando o usuário 2 examina a mesma página de tópico Neptune, seu modo de exibição difere do usuário 1.  O usuário 2 é capaz de ver o arquivo de *visão geral do produto DG-2000* na seção **arquivos fixos e páginas** da página de tópico, que não aparece para o usuário 1. 

![Tópico Neptune do usuário 2](../media/knowledge-management/user1-topic-view.png) </br> 

A diferença no que os usuários podem ver no mesmo tópico é porque os usuários podem não ter as permissões do Office 365 para exibir um site ou arquivo relacionado.  A experiência do tópico respeita as permissões que são definidas nos itens de um tópico e não podem alterar o acesso a elas. No nosso exemplo, o usuário 1 não pode exibir o arquivo de *visão geral do produto DG-2000* na página de tópico para Neptune porque o usuário 1 não tem as permissões do Office 365 para exibir o arquivo.

Se um usuário não conseguir ver informações suficientes em um tópico para ser útil, o tópico não estará disponível para o usuário. Nesse caso, o usuário não verá o tópico realçado. No entanto, um usuário diferente que tenha permissões para obter mais informações no tópico para que ele seja útil, poderá ver o tópico.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Permissões de tópico para gerentes de conhecimento e colaboradores de tópico

Os usuários que receberam permissões para gerenciar tópicos-gerentes de conhecimento – só poderão exibir as informações que têm permissões para ver nos tópicos.

Da mesma forma, os usuários que têm permissões de criação e edição de tópico – os colaboradores do tópico só poderão exibir as informações que têm permissões para ver nos tópicos. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus informações de tópico organizadas manualmente

Os tópicos podem conter informações geradas pelo AI e informações adicionadas ou editadas por colaboradores de tópico ou gerentes de conhecimento.

 - As informações de um tópico que foram adicionadas pelo AI são visíveis apenas para pessoas que têm acesso ao conteúdo de origem.
 - As informações que foram adicionadas ou editadas manualmente por um tópico Contribuidor ou gerente de conhecimento estão visíveis para todas as pessoas que podem ver o tópico.

A tabela a seguir descreve quais usuários – visualizadores de tópicos, colaboradores e gerentes de conhecimento-podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se tiverem uma relevância baixa para o usuário.|
|Descrição do tópico|As descrições geradas pelo AI são visíveis apenas para os usuários que têm permissões para o conteúdo de origem. Descrições inseridas ou editadas manualmente são visíveis para todos os usuários.|
|Pessoas|Pessoas fixas estão visíveis para todos os usuários. As pessoas sugeridas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|




## <a name="see-also"></a>Confira também

