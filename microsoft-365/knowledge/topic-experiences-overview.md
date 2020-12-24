---
title: Visão geral da experiência do tópico (versão prévia)
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
description: Visão geral das experiências de tópicos.
ms.openlocfilehash: 8b06dd016295c8b0712a7c18c2296a318cd826ba
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731314"
---
# <a name="topic-experiences-overview-preview"></a>Visão geral da experiência do tópico (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).

As experiências de tópico usam a tecnologia Microsoft AI, a Microsoft 365, o Delve, o Microsoft Graph, a pesquisa e outros componentes e serviços para criar uma rede de conhecimento em seu ambiente do Microsoft 365. 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Seu objetivo é converter informações em conhecimento e fornecê-las aos seus usuários em aplicativos que usam diariamente, como páginas modernas do SharePoint e pesquisa da Microsoft.

As experiências de tópico ajudam a lidar com um problema de negócios principal em muitas empresas, fornecendo as informações aos usuários quando eles precisam. Por exemplo, novos funcionários precisam aprender muitas novas informações rapidamente e encontrar termos que não conhecem nada sobre ao ler as informações da empresa. Para saber mais, o usuário pode precisar sair do que está fazendo e gastar um tempo valioso procurando por detalhes, como informações sobre o que é o termo, quem é especialista no assunto, e talvez sites e documentos que estão relacionados ao termo.

A experiência do tópico usa o AI para pesquisar e identificar **Tópicos** automaticamente em sua organização. Ele compila as informações sobre elas, como uma breve descrição, especialistas no assunto e sites, arquivos e páginas que estão relacionados a ele. Um gerente de conhecimento ou colaborador pode optar por atualizar as informações do tópico, conforme necessário. Os tópicos estão disponíveis para os usuários, o que significa que, para cada instância do tópico que aparece em um site moderno do SharePoint em notícias e páginas, o texto será realçado. Os usuários podem optar por selecionar o tópico para saber mais sobre ele por meio dos detalhes do tópico. Os tópicos também podem ser encontrados na pesquisa do SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Como os tópicos são exibidos para os usuários

Quando um tópico é mencionado em conteúdo nas notícias e páginas do SharePoint, você o verá realçado. Você pode abrir o resumo do tópico no destaque. Abra o tópico detalhes do título do resumo. O tópico mencionado pode ser identificado automaticamente ou adicionado à página com uma referência direta ao tópico pelo autor da página. 

   ![Destaques do tópico](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indexação de conhecimento

A experiência do tópico usa a tecnologia Microsoft AI para identificar os **Tópicos** no seu ambiente do Microsoft 365.

Um tópico é uma frase ou um termo que é organizacional significativo ou importante. Ele tem um significado específico para a organização e tem recursos relacionados a ele que podem ajudar as pessoas a entender o que é e encontrar mais informações sobre ele.

Quando um tópico é identificado e o AI determina que ele tem informações suficientes para ser um tópico sugerido, uma **página de tópico** é criada para ele que contém informações que foram coletadas por meio da indexação de tópicos, como:

- Nomes alternativos e/ou acrônimos.
- Uma breve descrição do tópico.
- Usuários que podem ter conhecimento do tópico.
- Arquivos, páginas e sites relacionados ao tópico.

Seus administradores de conhecimento podem optar por rastrear todos os sites do SharePoint em seu locatário para tópicos ou apenas selecionar determinados itens.

## <a name="roles"></a>Funções

Quando você usar experiências de tópico no seu ambiente Microsoft 365, seus usuários terão as seguintes funções:

- Visualizador de tópicos: usuários que conseguirão ver destaques de tópicos em sites modernos do SharePoint que tenham pelo menos acesso de *leitura* ao e no Microsoft Search. Eles poderão selecionar destaques do tópico para ver os detalhes do tópico nas páginas do tópico. Os visualizadores de tópicos poderão fornecer comentários sobre a utilidade de um tópico.

- Colaboradores: usuários que têm direitos para editar tópicos existentes ou criar novos. Administradores de conhecimento atribuem permissões de colaborador aos usuários por meio do tópico experiências de configurações no centro de administração do Microsoft 365. Observe que você também pode optar por permitir que todos os usuários do tópico editem e criem tópicos para que eles também possam contribuir para os tópicos que eles veem.

- Gerentes de conhecimento: usuários que orientam os tópicos por meio do ciclo de vida do tópico. Os gerentes de conhecimento usam a página **gerenciar tópicos** no centro de tópico para confirmar ou remover tópicos sugeridos do Ai, bem como editar tópicos existentes ou criar novos, e são os únicos usuários que têm acesso a ele. Administradores de conhecimento atribuem permissões de gerentes de conhecimento aos usuários pelo tópico experiências de administração no centro de administração do Microsoft 365. 

- Administradores de conhecimento: os administradores de conhecimento configuram experiências de tópico e o gerenciam através dos controles de administrador no centro de administração do Microsoft 365. Atualmente, um administrador global do Microsoft 365 ou do SharePoint pode servir como um administrador de conhecimento.

Consulte [tópico experiências funções](topic-experiences-roles.md) para obter mais informações.

## <a name="topic-management"></a>Gerenciamento de tópicos

O gerenciamento de tópicos é feito na página **gerenciar tópicos** no centro de **Tópicos** da sua organização. O tópico central é criado durante a instalação e serve como seu centro de conhecimento para sua organização. 

Embora todos os usuários licenciados possam ver os tópicos com os quais estão conectados no centro de tópicos, somente os usuários com permissões *gerenciar tópicos* (gerentes de conhecimento) poderão exibir e usar a página Gerenciar tópicos.

Os gerentes de conhecimento poderão:

- Confirmar ou rejeitar tópicos que foram descobertos em seu locatário.
- Crie novos tópicos manualmente, conforme necessário (por exemplo, se não forem fornecidas informações suficientes para serem descobertas por meio do AI).
- Editar páginas de tópico existentes.</br>

Consulte [gerenciar tópicos no tópico central](manage-topics.md) para obter mais informações.  


## <a name="admin-controls"></a>Controles de administrador

Os controles de administrador no centro de administração do Microsoft 365 permitem que você gerencie sua rede de conhecimento. Eles permitem que um administrador global do Microsoft 365 ou do SharePoint:

- Controlar quais usuários da sua organização podem ver os tópicos nas páginas modernas do SharePoint ou nos resultados de pesquisa do SharePoint.
- Controlar quais sites do SharePoint serão rastreados para Pesquisar tópicos.
- Configure o tópico Discovery para excluir tópicos específicos de serem localizados.
- Controlar quais usuários podem gerenciar tópicos no centro de tópicos.
- Controlar quais usuários podem criar e editar tópicos no centro de tópicos.
- Controle qual usuário poderá exibir tópicos.

Consulte [atribuir permissões de usuário](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions), [gerenciar visibilidade de tópico](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)e [gerenciar descoberta de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) para obter mais informações sobre controles de administrador.

## <a name="topic-curation--feedback"></a>Opinião sobre & de tópicos

O AI funcionará continuamente para fornecer sugestões para melhorar seus tópicos à medida que as alterações ocorrerem em seu ambiente. 

Os usuários que permitem o acesso para ver os tópicos em seus trabalhos diários podem ser solicitados se o tópico foi útil para eles. O AI examina essas respostas e as usa para ajudar a determinar o que é mostrado nos resumos de tópicos e nos detalhes do tópico.

Os usuários com permissões para editar ou criar tópicos podem fazer atualizações nas páginas de tópicos diretamente, caso pretendam fazer correções ou adicionar mais informações. 

Além disso, os usuários com permissões adequadas podem marcar itens como a conversa do Yammer que são relevantes para um tópico e adicioná-los a um tópico específico. 


## <a name="see-also"></a>Confira também

