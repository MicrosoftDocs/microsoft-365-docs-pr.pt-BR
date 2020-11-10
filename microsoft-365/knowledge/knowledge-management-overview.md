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
ms.openlocfilehash: 27ce6457f2329ccaa4738d6868b4f2051c0c0a51
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988837"
---
# <a name="knowledge-management-overview-preview"></a>Visão geral do gerenciamento de conhecimento (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).

O gerenciamento de conhecimento usa a tecnologia Microsoft AI, a Microsoft 365, o Delve, Pesquisar e outros componentes e serviços para criar uma rede de conhecimento em seu ambiente do Microsoft 365. 

   ![Fluxo de gerenciamento de conhecimento](../media/content-understanding/knowledge-management-flowchart.png) </br> 

É a meta de fornecer informações aos usuários nos aplicativos que usam diariamente, como o Outlook, o Teams e o SharePoint.

Por exemplo, os usuários visualizam termos não familiares em seus emails, sites do SharePoint ou em conversas do Teams, que desejam saber mais. O gerenciamento de conhecimento usa o AI para pesquisa e identifica automaticamente esses **Tópicos** , e compila as informações sobre eles, como uma breve descrição, especialistas no assunto e sites, arquivos e páginas relacionados a ele. Você pode optar por atualizar as informações do tópico, conforme necessário. Em seguida, você pode disponibilizar os tópicos aos usuários, o que significa que, para cada instância do tópico que aparece em aplicativos como Outlook, Teams e SharePoint, o texto será realçado. Os usuários podem optar por selecionar o tópico para saber mais sobre ele por meio dos detalhes do tópico.


## <a name="topic-indexing"></a>Indexação de tópicos

O gerenciamento de conhecimento usa a tecnologia Microsoft AI para identificar os **Tópicos** no seu ambiente do Office 365.

Um tópico é uma frase ou um termo que é organizacional significativo ou importante. Ele tem um significado específico para a organização e tem recursos relacionados a ele que podem ajudar as pessoas a entender o que é e encontrar mais informações sobre ele.

Quando um tópico é identificado, uma **página de tópico** é criada para ele contendo informações que foram coletadas por meio da indexação de tópicos, como:

- Nomes alternativos e/ou acrônimos.
- Uma breve descrição do tópico.
- Usuários que podem ter conhecimento do tópico.
- Arquivos, páginas e sites relacionados ao tópico.


## <a name="topic-discovery"></a>Descoberta de tópicos
Quando um tópico é mencionado em conteúdo nas notícias e páginas do SharePoint, você o verá realçado. Abra o resumo do tópico no destaque. Abra o tópico detalhes do título do resumo. <!--(msg for Efren: not sure if I should use discovery for this; we use discovered in-product for indexing?)--> O tópico mencionado pode ser identificado automaticamente ou adicionado à página com uma referência direta ao tópico pelo autor da página.

Você também pode descobrir tópicos por meio da pesquisa da Microsoft.


## <a name="topic-management"></a>Gerenciamento de tópicos

O gerenciamento de tópicos é feito no **centro de tópicos** da sua organização. O site do centro de tópicos é criado durante a instalação e serve como seu centro de conhecimento para sua organização. Ele conterá uma lista de todos os tópicos que foram descobertos em seu ambiente, bem como todas as páginas de tópicos que foram criadas para esses tópicos. 

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

Consulte [gerenciar sua rede de conhecimento](topic-experiences-discovery.md) para obter mais informações. 

## <a name="topic-curation--feedback"></a>Opinião sobre & de tópicos

O AI funcionará continuamente para fornecer sugestões para melhorar seus tópicos à medida que as alterações ocorrerem em seu ambiente.

Os usuários que permitem o acesso para ver os tópicos em seus trabalhos diários têm permissão para fazer sugestões para melhorá-los. Por exemplo, se um usuário exibir a página de tópico e ver informações incorretas ou que precisam ser adicionadas, um link na página de tópico permitirá que elas editem as informações diretamente. Outro exemplo, se um usuário exibir um destaque em uma página de notícias do SharePoint, você encontrará perguntas perguntando se o realce é ou não ou o tópico sugerido é apropriado para sua organização. A resposta ajudará a determinar o que é mostrado nos resumos de tópicos e nos detalhes do tópico.

Além disso, os usuários com permissões adequadas podem marcar itens como a conversa do Yammer que são relevantes para um tópico e adicioná-los a um tópico específico. <!--(msg for Efren: changed to Yammer, because we will not have shipped Teams yet)-->


## <a name="see-also"></a>Confira também
[Configurar o gerenciamento de conhecimento](set-up-topic-experiences.md)</br>
[Visão geral do centro de tópicos](topic-center-overview.md)
