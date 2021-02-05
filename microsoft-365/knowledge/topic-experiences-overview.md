---
title: Visão geral dos tópicos do Microsoft Viva
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
- m365initiative-topics
localization_priority: None
description: Visão geral dos tópicos do Viva.
ms.openlocfilehash: f45e0f7c6090d4584526aa9c2abb5ec98213d635
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107631"
---
# <a name="microsoft-viva-topics-overview"></a>Visão geral dos tópicos do Microsoft Viva 

Os tópicos do Viva usam a tecnologia Microsoft AI, Microsoft 365, Microsoft Graph, Pesquisa e outros componentes e serviços para trazer conhecimento aos usuários nos aplicativos do Microsoft 365 que usam todos os dias, começando com páginas modernas do SharePoint e Pesquisa da Microsoft.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Os Tópicos do Viva ajudam a resolver um problema comercial importante em muitas empresas, fornecendo as informações aos usuários quando necessário. Por exemplo, novos funcionários precisam aprender rapidamente muitas informações novas e encontrar termos sobre os quais não conhecem ao ler as informações da empresa. Para saber mais, o usuário pode precisar se afastar do que está fazendo e gastar muito tempo procurando detalhes, como informações sobre o termo, quem na organização é um especialista no assunto e talvez sites e documentos relacionados ao termo.

Os Tópicos do Viva usam a IA para procurar e identificar **automaticamente tópicos** em sua organização. Ele compila informações sobre eles, como uma breve descrição, pessoas que trabalham no tópico e sites, arquivos e páginas relacionadas a ele. Um gerente de conhecimento ou colaborador pode optar por atualizar as informações do tópico conforme necessário. Os tópicos estão disponíveis para seus usuários, o que significa que, para cada instância do tópico que aparece em um site moderno do SharePoint em notícias e páginas, o texto será realçado. Os usuários podem optar por selecionar o tópico para saber mais sobre ele por meio dos detalhes do tópico. Os tópicos também podem ser encontrados na Pesquisa do SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Como os tópicos são exibidos para os usuários

Quando um tópico é mencionado no conteúdo de notícias e páginas do SharePoint, você o verá realçado. Você pode abrir o resumo do tópico no destaque. Abra os detalhes do tópico no título do resumo. O tópico mencionado pode ser identificado automaticamente ou ter sido adicionado à página com uma referência direta ao tópico pelo autor da página. 

   ![Destaques de tópico](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indexação de conhecimento

Os tópicos do Viva usam a tecnologia microsoft AI para identificar **tópicos** em seu ambiente do Microsoft 365.

Um tópico é uma frase ou termo que é organizacionalmente significativo ou importante. Ela tem um significado específico para a organização e tem recursos relacionados a ela que podem ajudar as pessoas a entender o que são e encontrar mais informações sobre ela. Há vários tipos diferentes de tópicos que serão importantes para sua organização. Inicialmente, a tecnologia de IA da Microsoft se concentra nos seguintes tipos:
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
- Pessoas que podem estar experientes sobre o tópico.
- Arquivos, páginas e sites relacionados ao tópico.

Os administradores de conhecimento podem optar por rastrear todos os sites do SharePoint em seu locatário para tópicos ou apenas selecionar determinados.

Consulte [Descoberta e cura de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Funções

Quando você usa Tópicos do Viva em seu ambiente do Microsoft 365, os usuários terão as seguintes funções:

- Visualizadores de tópicos: usuários que podem ver destaques  de tópico em sites modernos do SharePoint aos que têm pelo menos acesso de leitura e na Pesquisa da Microsoft. Eles podem selecionar destaques de tópicos para ver detalhes do tópico nas páginas de tópicos. Os visualizadores de tópicos podem fornecer comentários sobre como um tópico é útil para eles.

- Colaboradores: usuários que têm direitos para editar tópicos existentes ou criar novos. Os administradores de conhecimento atribuem permissões de colaborador aos usuários por meio das configurações de Tópicos do Viva no centro de administração do Microsoft 365. Observe que você também pode optar por dar a todos os visualizadores de tópicos a permissão para editar e criar tópicos para que todos possam contribuir com os tópicos que eles veem.

- Gerentes de conhecimento: usuários que orientam tópicos no ciclo de vida do tópico. Gerentes de conhecimento usam a página Gerenciar **Tópicos** na Central de Tópicos para confirmar tópicos sugeridos por IA, remover tópicos que não são mais relevantes, bem como editar tópicos existentes ou criar novos e são os únicos usuários que têm acesso a ele. Os administradores de conhecimento atribuem permissões de gerente de conhecimento aos usuários por meio das configurações de administrador do Viva Topics no Centro de administração do Microsoft 365. 

- Administradores de conhecimento: administradores de conhecimento configuram tópicos do Viva e os gerenciam por meio dos controles de administrador no centro de administração do Microsoft 365. Atualmente, um administrador global do Microsoft 365 ou do SharePoint pode servir como administrador de conhecimento.

Confira [as funções de Tópicos do Viva](topic-experiences-roles.md) para obter mais informações.

## <a name="topic-management"></a>Gerenciamento de tópicos

O gerenciamento de tópicos é feito **na página Gerenciar tópicos** no Centro de **Tópicos da sua organização.** A Central de Tópicos é criada durante a instalação e serve como centro de conhecimento para sua organização. 

Embora todos os usuários licenciados possam ver tópicos aos que estão conectados na Central de *Tópicos,* somente os usuários com permissões Gerenciar tópicos (gerentes de conhecimento) podem exibir e usar a página Gerenciar tópicos.

Os gerentes de conhecimento podem:

- Confirme ou remova tópicos descobertos em seu locatário.
- Crie novos tópicos manualmente conforme necessário (por exemplo, se não foram fornecidas informações suficientes para que eles sejam descobertos por meio da ia).
- Editar páginas de tópicos existentes.</br>

Consulte [Gerenciar tópicos na Central de Tópicos](manage-topics.md) para obter mais informações.  


## <a name="admin-controls"></a>Controles de administração

Os controles de administrador no Centro de administração do Microsoft 365 permitem que você gerencie sua rede de conhecimento. Eles permitem que um administrador global do Microsoft 365 ou do SharePoint:

- Controlar quais usuários em sua organização têm permissão para ver tópicos em páginas modernas do SharePoint ou nos resultados de pesquisa do SharePoint.
- Controlar quais sites do SharePoint serão rastreados para identificar tópicos.
- Exclua tópicos específicos de serem encontrados.
- Controlar quais usuários podem gerenciar tópicos no centro de tópicos.
- Controlar quais usuários podem criar e editar tópicos.
- Controlar qual usuário pode exibir tópicos.

Consulte [atribuir permissões de usuário,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)gerenciar [visibilidade do](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)tópico e gerenciar a descoberta de [tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) para obter mais informações sobre controles de administrador.

## <a name="topic-curation--feedback"></a>Comentários sobre a & tópico

A IA trabalhará continuamente para fornecer sugestões para melhorar seus tópicos à medida que as alterações ocorrerem em seu ambiente. 

Os usuários com permissões de edição ou criação de tópicos podem fazer atualizações em páginas de tópicos diretamente se quiserem fazer correções ou adicionar informações adicionais. Eles também podem adicionar novos tópicos que a IA não conseguiu identificar. Se houver informações suficientes sobre esses tópicos adicionados manualmente e a IA for capaz de identificar esse tipo de tópico, sugestões adicionais da IA poderão aprimorar esses tópicos adicionados manualmente 

Os usuários que você permite o acesso para ver tópicos em seu trabalho diário podem ser solicitados se o tópico foi útil para eles. O sistema analisa essas respostas e as usa para melhorar o destaque do tópico e ajudar a determinar o que é mostrado nos resumos de tópicos e nos detalhes do tópico.

Além disso, os usuários com permissões adequadas podem marcar itens como conversas do Yammer que são relevantes para um tópico e adicioná-los a um tópico específico. 

Consulte [a descoberta e a cura de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Confira também

