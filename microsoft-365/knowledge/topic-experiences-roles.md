---
title: Funções de Tópicos do Microsoft Viva
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
description: Saiba mais sobre funções de usuário em Tópicos do Viva.
ms.openlocfilehash: 6d93046a96b60779c3cd3bd6c6aa600cb443118f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917351"
---
# <a name="microsoft-viva-topics-roles"></a>Funções de Tópicos do Microsoft Viva 

Quando você usa Tópicos do Viva em seu ambiente do Microsoft 365, seus usuários podem ter as seguintes funções:
-   Visualizador de tópicos
-   Colaborador de tópicos
-   Gerente de conhecimento
-   Administrador de conhecimento

## <a name="topic-viewer"></a>Visualizador de tópicos

Os visualizadores de tópicos são usuários em sua organização que podem exibir tópicos destacados em seu site moderno do SharePoint, Pesquisa da Microsoft através do SharePoint e Office.com e o centro de tópicos. Eles podem exibir mais detalhes sobre um tópico na página de tópicos. 

Para que os destaques de tópicos e suas páginas de tópicos sejam visíveis para um visualizador de tópicos, o usuário deve:
-   [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador do Microsoft 365.
-   Ter permissão para ter visibilidade para tópicos. Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.


## <a name="topic-contributors"></a>Colaboradores de tópicos

Colaboradores de tópicos são usuários em sua organização que não só têm permissões de visualizador de tópicos, mas também podem editar um tópico existente ou criar um novo tópico. Eles têm uma função importante na "cura" manualmente das informações em uma página de tópicos (AI ou fornecida manualmente) para garantir sua qualidade.

Os usuários que têm permissões de colaborador de tópicos verão um botão **Editar** exibido em páginas de tópicos, que permite que eles façam atualizações e publiquem um tópico.

Um colaborador de tópicos também pode criar e publicar um novo tópico por meio do centro de tópicos.

Para criar e editar um tópico, o usuário deve:

-   [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador do Microsoft 365.
-   [Sejam atribuídas permissões para criar e editar tópicos](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center). Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.

## <a name="knowledge-managers"></a>Gerentes de conhecimento

Os gerentes de conhecimento são usuários que gerenciam tópicos em sua organização.  O gerenciamento de tópicos é feito por meio da página Gerenciar Tópicos no centro de tópicos e só fica visível para gerentes de Conhecimento.

Na página Gerenciar Tópicos, os gerentes de conhecimento podem realizar as seguintes tarefas:
-   Exibir tópicos sugeridos por IA.
-   Revise tópicos para confirmar se eles são válidos.
-   Remova os tópicos que você não deseja que visem aos usuários.

Além disso, um gerente de conhecimento pode editar tópicos existentes ou criar novos.

Para gerenciar tópicos, o usuário deve:
-   [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador do Microsoft 365.
-   [Sejam atribuídas permissões para gerenciar tópicos](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.

Os usuários que têm um bom conhecimento geral da sua empresa podem ser bons candidatos para a função de gerente de conhecimento. Essas pessoas podem não apenas ter o conhecimento para saber se os tópicos são válidos ou não, mas também podem conhecer pessoas dentro da empresa que estão relacionadas a esses tópicos.


## <a name="knowledge-admins"></a>Administradores de conhecimento

Os administradores de conhecimento são administradores que configuram e configuram Tópicos do Viva em seu ambiente do Microsoft 365. Eles também gerenciam as configurações de Tópicos do Viva após a conclusão da configuração. A função de administrador de conhecimento exige que você seja um administrador global do Microsoft 365 ou do SharePoint, já que a instalação e o gerenciamento são feitos no centro de administração do Microsoft 365.
Durante a instalação, os administradores de conhecimento podem configurar Tópicos do Viva para:

-   Selecione quais sites do SharePoint serão rastreados para tópicos.
-   Selecione quais usuários licenciados podem exibir tópicos (visualizadores de tópicos).
-   Selecione quais tópicos serão excluídos de serem identificados.
-   Selecione quais usuários licenciados podem criar e editar tópicos (colaboradores de tópicos).
-   Selecione quais usuários licenciados podem gerenciar tópicos (gerentes de conhecimento).
-   Nomeia o centro de tópicos.

Os gerentes de conhecimento precisam ser capazes de coordenar com todos os participantes do Viva Topics em sua organização para saber como configurá-lo. Por exemplo, se um novo projeto tiver informações confidenciais, o gerente de conhecimento precisará ser informado para garantir que o site do SharePoint não seja rastreado para tópicos ou nomes de tópicos específicos precisem ser excluídos.


## <a name="see-also"></a>Confira também