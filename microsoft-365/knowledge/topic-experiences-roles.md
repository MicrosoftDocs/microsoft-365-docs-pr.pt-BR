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
ms.openlocfilehash: 9f1d3667ee9eeb05201613c15dc360b2b006cecb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288066"
---
# <a name="microsoft-viva-topics-roles"></a>Funções de Tópicos do Microsoft Viva 

Quando você usa Tópicos do Viva em seu ambiente Microsoft 365, os usuários podem ter as seguintes funções:

- Visualizador de tópicos
- Colaborador de tópicos
- Gerente de conhecimento
- Administrador de conhecimento

## <a name="topic-viewer"></a>Visualizadores de tópicos

Os visualizadores de tópicos são usuários em sua organização que podem exibir tópicos destacados em seu site SharePoint moderno, Pesquisa da Microsoft por meio de SharePoint e Office.com e o centro de tópicos. Eles podem exibir mais detalhes sobre um tópico na página de tópicos. 

Para os destaques de tópicos e suas páginas de tópicos ficarem visíveis para um visualizador de tópicos, o usuário precisa:

- [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador Microsoft 365.
- Ter permissão de visibilidade dos tópicos. Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.

## <a name="topic-contributors"></a>Colaboradores de tópicos

Os colaboradores de tópicos são usuários de sua organização que não apenas têm as permissões do visualizador de tópicos, mas também podem editar um tópico existente ou criar um novo tópico. Eles têm uma função importante na "cura" manualmente das informações em uma página de tópicos (AI ou fornecida manualmente) para garantir sua qualidade.

Os usuários que têm permissões de colaborador de tópicos verão um botão **Editar** exibido em páginas de tópicos, que permite que eles façam atualizações e publiquem um tópico.

Um colaborador de tópicos também pode criar e publicar um novo tópico por meio de seu centro de tópicos.

Para criar e editar um tópico, o usuário deve:

- [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador Microsoft 365.
- [Sejam atribuídas permissões para criar e editar tópicos](./topic-experiences-user-permissions.md). Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.

## <a name="knowledge-managers"></a>Gerentes de conhecimento

Os gerentes de conhecimento são usuários que gerenciam tópicos na sua organização.  O gerenciamento de tópicos é feito por meio da página Gerenciar Tópicos no centro de tópicos, que só fica visível para os gerentes de conhecimento.

Na página Gerenciar Tópicos, os gerentes de conhecimento podem executar as seguintes tarefas:

- Visualizar tópicos sugeridos por IA.
- Revise tópicos para confirmar se eles são válidos.
- Remova os tópicos que você não deseja que visem aos usuários.

Além disso, um gerente de conhecimento pode editar tópicos existentes ou criar novos.

Para gerenciar tópicos, o usuário deve:

- [Seja atribuída uma licença de Tópicos do Viva](./set-up-topic-experiences.md#assign-licenses) pelo administrador Microsoft 365.
- [Sejam atribuídas permissões para gerenciar tópicos](./topic-experiences-user-permissions.md)). Essa tarefa é feita pelo administrador de conhecimento na página de configurações de Tópicos do Viva no Centro de administração do Microsoft 365.

Os usuários que têm um bom conhecimento geral da sua empresa podem ser bons candidatos para a função de gerente de conhecimento. Essas pessoas podem não apenas ter o conhecimento para saber se os tópicos são válidos ou não, mas também podem conhecer pessoas dentro da empresa que estão relacionadas a esses tópicos.

## <a name="knowledge-admins"></a>Administradores de conhecimento

Os administradores de conhecimento são administradores que configuram e configuram Tópicos do Viva em seu Microsoft 365 ambiente. Eles também gerenciam as configurações de Tópicos do Viva após a conclusão da configuração. A função de administrador de conhecimento exige que você seja um administrador Microsoft 365 global ou SharePoint uma vez que a instalação e o gerenciamento são feitos no Centro de administração do Microsoft 365.
Durante a instalação, os administradores de conhecimento podem configurar Tópicos do Viva para:

- Selecionar quais sites do SharePoint serão rastreados para identificar tópicos.
- Selecionar quais usuários licenciados podem visualizar tópicos (visualizadores de tópicos).
- Selecionar quais tópicos serão excluídos da identificação.
- Selecionar quais usuários licenciados podem criar e editar tópicos (colaboradores de tópicos).
- Selecionar quais usuários licenciados podem gerenciar tópicos (gerentes de conhecimento).
- Nomeia o centro de tópicos.

Os gerentes de conhecimento precisam ser capazes de coordenar todas as partes interessadas em tópicos do Microsoft Viva em sua organização para saber como configurá-los. Por exemplo, se um novo projeto tiver informações confidenciais, o gerente de conhecimento precisará ser informado para que ele possa garantir que o site do SharePoint não seja rastreado para tópicos ou nomes de tópicos específicos precisem ser excluídos.
