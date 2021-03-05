---
title: Visão geral de Tópicos do Microsoft Viva
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Visão geral dos tópicos do Viva.
ms.openlocfilehash: 91442ba12b3d5df1d9934022751f4bc381cd40e8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453964"
---
# <a name="microsoft-viva-topics-overview"></a>Visão geral de Tópicos do Microsoft Viva 

Os Tópicos do Viva usam a tecnologia Microsoft AI, Microsoft 365, Microsoft Graph, Search e outros componentes e serviços para trazer conhecimento aos seus usuários nos aplicativos do Microsoft 365 que eles usam diariamente, começando com páginas modernas do SharePoint e Pesquisa da Microsoft.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Os Tópicos do Viva ajudam a resolver um problema comercial importante em muitas empresas , fornecendo as informações aos usuários quando precisam. Por exemplo, novos funcionários precisam aprender muitas informações novas rapidamente e encontrar termos sobre os quais eles não conhecem ao ler as informações da empresa. Para saber mais, o usuário pode precisar se afastar do que está fazendo e gastar um tempo valioso procurando detalhes, como informações sobre o termo, quem na organização é um especialista em assuntos e, talvez, sites e documentos relacionados ao termo.

Os Tópicos do Viva usam a IA para pesquisar automaticamente e identificar **tópicos** em sua organização. Ele compila informações sobre eles, como uma breve descrição, pessoas que trabalham no tópico e sites, arquivos e páginas relacionadas a ele. Um gerente de conhecimento ou colaborador pode optar por atualizar as informações do tópico conforme necessário. Os tópicos estão disponíveis para seus usuários, o que significa que, para cada instância do tópico que aparece em um site moderno do SharePoint em notícias e páginas, o texto será realçado. Os usuários podem optar por selecionar o tópico para saber mais sobre ele por meio dos detalhes do tópico. Os tópicos também podem ser encontrados na Pesquisa do SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Como os tópicos são exibidos para os usuários

Quando um tópico é mencionado em conteúdo em notícias e páginas do SharePoint, você o verá realçado. Você pode abrir o resumo do tópico no destaque. Abra os detalhes do tópico a partir do título do resumo. O tópico mencionado poderia ser identificado automaticamente ou ter sido adicionado à página com uma referência direta ao tópico pelo autor da página. 

   ![Destaques de tópicos](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indexação de conhecimento

O Viva Topics usa a tecnologia Microsoft AI para identificar **tópicos** em seu ambiente do Microsoft 365.

Um tópico é uma frase ou termo que é organizacionalmente significativo ou importante. Ele tem um significado específico para a organização e tem recursos relacionados a ela que podem ajudar as pessoas a entender o que são e encontrar mais informações sobre ela. Há vários tipos diferentes de tópicos que serão importantes para sua organização. Inicialmente, a tecnologia da Microsoft AI se concentra nos seguintes tipos:
- Project
- Evento
- Organização
- Localização
- Produto
- Trabalho criativo
- Campo de estudo


Quando um tópico é identificado e a IA determina que ele tem  informações suficientes para ser um tópico sugerido, uma página de tópico exibe as informações coletadas por meio da indexação de tópicos, como:

- Nomes alternativos e acrônimos.
- Uma breve descrição do tópico.
- Pessoas que podem ter conhecimento sobre o tópico.
- Arquivos, páginas e sites relacionados ao tópico.

Os administradores de conhecimento podem optar por rastrear todos os sites do SharePoint em seu locatário para tópicos ou apenas selecionar determinados.

Consulte [Descoberta e cura de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Funções

Quando você usa Tópicos do Viva em seu ambiente do Microsoft 365, seus usuários terão as seguintes funções:

- Visualizadores de tópicos: os usuários que podem ver destaques de tópicos em sites modernos do SharePoint aos que têm pelo menos acesso de leitura e na Pesquisa da Microsoft.  Eles podem selecionar destaques de tópicos para ver detalhes do tópico nas páginas de tópicos. Os visualizadores de tópicos podem fornecer comentários sobre como um tópico é útil para eles.

- Colaboradores: usuários que têm direitos para editar tópicos existentes ou criar novos. Os administradores de conhecimento atribuem permissões de colaborador aos usuários por meio das configurações de Tópicos do Viva no Centro de administração do Microsoft 365. Observe que você também pode optar por dar a todos os visualizadores de tópicos a permissão para editar e criar tópicos para que todos possam contribuir com os tópicos que eles veem.

- Gerentes de conhecimento: usuários que orientam tópicos pelo ciclo de vida do tópico. Os gerentes de conhecimento usam a página Gerenciar **Tópicos** na Central de Tópicos para confirmar tópicos sugeridos pela IA, remover tópicos que não são mais relevantes, bem como editar tópicos existentes ou criar novos e são os únicos usuários que têm acesso a ele. Os administradores de conhecimento atribuem permissões de gerenciador de conhecimento aos usuários por meio das configurações de administrador do Viva Topics no centro de administração do Microsoft 365. 

- Administradores de conhecimento: os administradores de conhecimento configuram Tópicos do Viva e gerenciam-os por meio dos controles de administrador no centro de administração do Microsoft 365. Atualmente, um administrador global ou do SharePoint do Microsoft 365 pode servir como administrador de conhecimento.

Confira [Funções de Tópicos do Viva](topic-experiences-roles.md) para obter mais informações.

## <a name="topic-management"></a>Gerenciamento de tópicos

O gerenciamento de tópicos é feito na página **Gerenciar tópicos** no Centro **de Tópicos da sua organização.** O Centro de tópicos é criado durante a instalação e serve como seu centro de conhecimento para sua organização. 

Embora todos os usuários licenciados possam ver tópicos com os que estão conectados no Centro de Tópicos, somente os usuários com permissões Gerenciar tópicos *(gerentes* de conhecimento) podem exibir e usar a página Gerenciar tópicos.

Os gerentes de conhecimento podem:

- Confirme ou remova tópicos que foram descobertos em seu locatário.
- Crie novos tópicos manualmente conforme necessário (por exemplo, se não foram fornecidas informações suficientes para que sejam descobertas por meio da AI).
- Editar páginas de tópicos existentes.</br>

Consulte [Gerenciar tópicos na central de tópicos](manage-topics.md) para obter mais informações.  


## <a name="admin-controls"></a>Controles de administrador

Os controles de administrador no Centro de administração do Microsoft 365 permitem que você gerencie sua rede de conhecimento. Eles permitem que um administrador global ou do SharePoint do Microsoft 365:

- Controlar quais usuários em sua organização têm permissão para ver tópicos em páginas modernas do SharePoint ou nos resultados da pesquisa do SharePoint.
- Controlar quais sites do SharePoint serão rastreados para identificar tópicos.
- Exclua tópicos específicos de serem encontrados.
- Controlar quais usuários podem gerenciar tópicos no centro de tópicos.
- Controlar quais usuários podem criar e editar tópicos.
- Controlar quais usuários podem exibir tópicos.

Confira [atribuir permissões de usuário,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)gerenciar [](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) [visibilidade de](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)tópico e gerenciar a descoberta de tópicos para obter mais informações sobre controles de administrador.

## <a name="topic-curation--feedback"></a>Curadoria de tópicos & comentários

A IA trabalhará continuamente para fornecer sugestões para melhorar seus tópicos à medida que as alterações ocorrem em seu ambiente. 

Os usuários com permissões de edição ou criação de tópicos podem fazer atualizações para páginas de tópicos diretamente se quiserem fazer correções ou adicionar informações adicionais. Eles também podem adicionar novos tópicos que a AI não foi capaz de identificar. Se houver informações suficientes sobre esses tópicos adicionados manualmente e a AI for capaz de identificar esse tipo de tópico, sugestões adicionais da AI podem aprimorar esses tópicos adicionados manualmente 

Os usuários que você permitem que o acesso vejam tópicos em seu trabalho diário podem ser perguntados se o tópico foi útil para eles. O sistema analisa essas respostas e as usa para melhorar o destaque do tópico e ajudar a determinar o que é mostrado nos resumos de tópicos e nos detalhes do tópico.

Além disso, os usuários com permissões adequadas podem marcar itens como conversas do Yammer relevantes para um tópico e adicioná-los a um tópico específico. 

Consulte [Descoberta e cura de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Confira também

