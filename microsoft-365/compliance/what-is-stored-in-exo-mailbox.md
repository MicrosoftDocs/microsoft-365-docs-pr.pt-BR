---
title: Conteúdo armazenado em caixas de correio do Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: O conteúdo produzido por aplicativos baseados em nuvem no Microsoft 365 é armazenado ou associado à caixa de correio do Exchange Online de um usuário. Esse conteúdo pode ser pesquisado usando ferramentas de Descoberta Online da Microsoft.
ms.openlocfilehash: 872e618486c273e07e8dcf98d61bbbb7d8f95051
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838604"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Conteúdo armazenado em caixas de correio do Exchange Online para Descoberta Virtual

Uma caixa de correio no Exchange Online é usada principalmente para armazenar itens relacionados a email, como mensagens, itens de calendário, tarefas e anotações. Mas isso está mudando à medida que mais aplicativos baseados em nuvem também armazenam seus dados na caixa de correio de um usuário. Uma vantagem de armazenar dados em uma caixa de correio é que você pode usar as ferramentas de pesquisa na pesquisa de conteúdo, Descoberta Principal e Descoberta Eletrônico Avançada para encontrar, exibir e exportar os dados desses aplicativos baseados em nuvem. Os dados de alguns desses aplicativos são armazenados em pastas ocultas localizadas em uma subárvore de mensagem não interpessoal (não-IPM) na caixa de correio. Os dados de outros aplicativos  baseados em nuvem  podem não ser armazenados na caixa de correio, mas estão associados à caixa de correio e são retornados em pesquisas (se esses dados coincidem com a consulta de pesquisa). Independentemente de os dados baseados em nuvem ser armazenados ou associados a uma caixa de correio de usuário, os dados normalmente não são visíveis em um cliente de email quando um usuário abre a caixa de correio.

A tabela a seguir lista os aplicativos que armazenam ou associam dados a uma caixa de correio baseada em nuvem. A tabela também descreve o tipo de conteúdo que cada aplicativo produz.

|Aplicativo do Microsoft 365|Descrição|
|:---------|:---------|
|Forms|Formulários e respostas a um formulário são armazenados em arquivos anexados a mensagens de email e armazenados em uma pasta oculta na caixa de correio do usuário que criou o formulário. Os formulários criados antes de abril de 2020 são armazenados como um arquivo PDF. Os formulários criados após 2020 são armazenados como um arquivo JSON.  As respostas a um formulário são armazenadas em um arquivo CSV. Quando você exporta conteúdo de Formulários em um arquivo PST, esses dados estão localizados na pasta **ApplicationDataRoot** em uma subpasta denominada com o seguinte GUID identificado globalmente: **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**. |
|Grupos do Microsoft 365|Mensagens de email, itens de calendário, contatos (Pessoas), anotações e tarefas são armazenadas na caixa de correio associada a um grupo do Microsoft 365.|
|Outlook/Exchange Online|Mensagens de email, itens de calendário, contatos (Pessoas), anotações e tarefas são armazenadas na caixa de correio de um usuário.|
|Pessoas|Os contatos no aplicativo Pessoas (que são os mesmos contatos que os acessíveis no Outlook) são armazenados na caixa de correio de um usuário.|
|Agendamento de Classe|Os planos criados no Agendamento de Classe são armazenados na caixa de correio do Grupo do Microsoft 365 correspondente que é provisionado quando um novo plano é criado. O alias da caixa de correio de grupo é o nome do plano.|
|Skype for Business|As conversas no Skype for Business são armazenadas na pasta Histórico da Conversa na caixa de correio de um usuário. Se a caixa de correio de um participante de uma reunião do Skype for colocada em Retenção de Litígio ou atribuída a uma política de retenção, os arquivos anexados a uma reunião serão mantidos na caixa de correio dos participantes.|
|Sway|Sways são armazenados como um arquivo HTML anexado a uma mensagem de email e armazenados em uma pasta oculta na caixa de correio do usuário que criou o sway. Quando você exporta conteúdo do Sway em um arquivo PST, esses dados estão localizados na pasta **ApplicationDataRoot** em uma subpasta denominada com o seguinte GUID:  **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tarefas|As tarefas no aplicativo Tarefas (que são as mesmas tarefas que as acessíveis no Outlook) são armazenadas na caixa de correio de um usuário.|
|Teams|As conversas que fazem parte de um canal do Teams estão associadas à caixa de correio do Teams. As conversas que fazem parte da lista chat no Teams (também chamadas *de chats 1 x N*) são associadas à caixa de correio dos usuários que participam do chat. Além disso, as informações de resumo para reuniões e chamadas em um canal do Teams estão associadas às caixas de correio de usuários que discam para a reunião ou chamada. Portanto, ao pesquisar o conteúdo do Teams, pesquise na caixa de correio do Teams o conteúdo em conversas de canal e pesquise as caixas de correio de usuários em busca de conteúdo em chats 1 x N.|
|Tarefa pendente|Tarefas (chamadas *de dos*, que são salvas em listas a fazer) no aplicativo To-Do são armazenadas na caixa de correio de um usuário.|
|Yammer|Conversas e comentários em uma comunidade do Yammer estão associados à caixa de correio do Grupo do Microsoft 365, bem como à caixa de correio do usuário do autor e a todos os destinatários nomeados (@ mencionados ou usuários cc'ed). As mensagens privadas enviadas fora de uma comunidade do Yammer são armazenadas na caixa de correio dos usuários que participam da mensagem privada.|  
||||

> [!NOTE]
> Neste momento, se uma responsabilidade for colocada em uma caixa de correio (usando ressarções em Casos de Descoberta Básica e Descoberta Avançada), o conteúdo de Forms e Sway não será preservado pela responsabilidade.
