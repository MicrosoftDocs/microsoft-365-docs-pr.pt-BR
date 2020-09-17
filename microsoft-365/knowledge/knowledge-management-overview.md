---
title: Visão geral do gerenciamento de conhecimento (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Visão geral do gerenciamento de conhecimento no Project Cortex.
ms.openlocfilehash: 80750ee94248b21b8ac7bd3869830a7986de34b9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949367"
---
# <a name="knowledge-management-0verview-preview"></a>0verview de gerenciamento de conhecimento (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex) 

O gerenciamento de conhecimento usa a tecnologia Microsoft AI, a Microsoft 365, o Delve, Pesquisar e outros componentes e serviços para criar uma rede de conhecimento em seu ambiente do Microsoft 365. 

   ![Fluxo de gerenciamento de conhecimento](../media/content-understanding/knowledge-management-flowchart.png) </br> 

É a meta de fornecer informações aos usuários nos aplicativos que usam diariamente, como o Outlook, o Teams e o SharePoint.

Por exemplo, os usuários visualizam termos não familiares em seus emails, sites do SharePoint ou em conversas do Teams, que desejam saber mais. O gerenciamento de conhecimento usa o AI para pesquisa e identifica automaticamente esses **Tópicos**, e compila as informações sobre eles, como uma breve descrição, especialistas no assunto e sites, arquivos e páginas relacionados a ele. Você pode optar por atualizar as informações do tópico, conforme necessário. Em seguida, você pode disponibilizar os tópicos aos usuários, o que significa que, para cada instância do tópico que aparece em aplicativos como Outlook, Teams e SharePoint, o texto será realçado. Os usuários podem optar por selecionar o tópico para saber mais sobre ele por meio dos detalhes do tópico.


## <a name="topic-discovery"></a>Descoberta de tópicos

O gerenciamento de conhecimento usa a tecnologia Microsoft AI para pesquisar **Tópicos** no seu ambiente do Office 365.

Um tópico é uma frase ou um termo que é organizacional significativo ou importante. Ele tem um significado específico para a organização e tem recursos relacionados a ele que podem ajudar as pessoas a entender o que é e encontrar mais informações sobre ele.

Quando um tópico é descoberto, uma **página de tópico** é criada para ele que contém informações que foram coletadas por meio da descoberta de tópicos, como:

- Uma breve descrição do tópico.
- Usuários que podem ter conhecimento do tópico.
- Arquivos, páginas e sites relacionados ao tópico.


## <a name="topic-management"></a>Gerenciamento de tópicos

O gerenciamento de tópicos é feito no **centro de tópicos**da sua organização. O site do centro de tópicos é criado durante a instalação e serve como seu centro de conhecimento para sua organização. Ele conterá uma lista de todos os tópicos que foram descobertos em seu ambiente, bem como todas as páginas de tópicos que foram criadas para esses tópicos. 

Os usuários que receberão as permissões corretas poderão fazer o seguinte no centro de tópicos:

- Confirmar ou rejeitar tópicos que foram descobertos em seu locatário.
- Crie novos tópicos manualmente, conforme necessário (por exemplo, se não forem fornecidas informações suficientes para serem descobertas por meio do AI).
- Editar páginas de tópico existentes.</br>

Confira [o tópico trabalhar com no tópico central](work-with-topics.md) para obter mais informações.  


## <a name="admin-controls"></a>Controles de administrador

Os controles de administrador no centro de administração do Microsoft 365 permitem que você gerencie sua rede de conhecimento. Eles permitem que um administrador global do Microsoft 365 ou do SharePoint:

- Controlar quais usuários da sua organização têm permissão para ver tópicos em seus aplicativos cliente ou nos resultados de pesquisa do SharePoint.
- Controlar quais sites do SharePoint serão rastreados para Pesquisar tópicos.
- Configure o tópico Discovery para excluir termos específicos que você não deseja que sejam um tópico.
- Controlar quais usuários podem confirmar ou rejeitar tópicos no centro de tópicos.
- Controlar quais usuários podem criar e editar tópicos no centro de tópicos.

Consulte [gerenciar sua rede de conhecimento](manage-knowledge-network.md) para obter mais informações. 

## <a name="topic-curation"></a>Organizada de tópicos

O AI funcionará continuamente para fornecer sugestões para melhorar seus tópicos à medida que as alterações ocorrerem em seu ambiente.

Os usuários que permitem o acesso para ver os tópicos em seus trabalhos diários têm permissão para fazer sugestões para melhorá-los. Por exemplo, se um usuário exibir a página de tópico e ver informações incorretas ou que precisam ser adicionadas, um link na página de tópico permite que eles enviem uma solicitação para atualizar as informações.

Além disso, os usuários com permissões adequadas podem marcar itens como conversa de equipes que são relevantes para um tópico e adicioná-los a um tópico específico.




## <a name="see-also"></a>Confira também
[Configurar o gerenciamento de conhecimento](set-up-knowledge-network.md)</br>
[Visão geral do centro de tópicos](topic-center-overview.md)
