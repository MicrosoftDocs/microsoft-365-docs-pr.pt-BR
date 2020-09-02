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
ROBOTS: NOINDEX, NOFOLLOW
description: Os dados produzidos por aplicativos baseados em nuvem no Microsoft 365 são armazenados ou associados à caixa de correio do Exchange Online de um usuário.
ms.openlocfilehash: 121380cdaaf5d0397d082159ddf6461c0c12cbe1
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321980"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Conteúdo armazenado em caixas de correio do Exchange Online

Uma caixa de correio no Exchange Online é usada principalmente para armazenar itens relacionados a email, como mensagens, itens de calendário, tarefas e anotações. Mas isso está mudando à medida que mais aplicativos baseados em nuvem também armazenam seus dados na caixa de correio de um usuário. Uma vantagem de armazenar dados em uma caixa de correio é que você pode usar as ferramentas de pesquisa em pesquisa de conteúdo, eDiscovery principal, descoberta eletrônica avançada e investigações de dados para localizar, exibir e exportar os dados desses aplicativos baseados em nuvem. Os dados de alguns desses aplicativos são armazenados em pastas ocultas localizadas em uma subárvore de mensagens não interpessoais (não-IPM) na caixa de correio. Dados de outros aplicativos baseados em nuvem podem não ser armazenados _na_ caixa de correio, mas são _associados_ à caixa de correio e retornados em pesquisas (se esses dados corresponderem à consulta de pesquisa). Independentemente de os dados baseados em nuvem estarem armazenados ou associados a uma caixa de correio de usuário, os dados normalmente não são visíveis em um cliente de email quando um usuário abre a caixa de correio.

A tabela a seguir lista os aplicativos que armazenam ou associam dados com uma caixa de correio baseada em nuvem. A tabela também descreve o tipo de conteúdo que cada aplicativo produz.

|Aplicativo Microsoft 365|Descrição|
|:---------|:---------|
|Formulários|Formulários e respostas a um formulário são armazenados em arquivos anexados a mensagens de email e armazenados em uma pasta oculta na caixa de correio do usuário que criou o formulário. Os formulários criados antes de abril de 2020 são armazenados como um arquivo PDF. Formulários criados após 2020 são armazenados como um arquivo JSON.  As respostas a um formulário são armazenadas em um arquivo CSV. Quando você exporta conteúdo de formulários em um arquivo PST, esses dados estão localizados na pasta **ApplicationDataRoot** em uma subpasta chamada com o seguinte identificado globalmente exclusivo (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Grupos do Microsoft 365|Mensagens de email, itens de calendário, contatos (pessoas), anotações e tarefas são armazenados na caixa de correio associada a um grupo do Microsoft 365.|
|Outlook/Exchange Online|Mensagens de email, itens de calendário, contatos (pessoas), anotações e tarefas são armazenados na caixa de correio de um usuário.|
|Pessoas|Contatos no aplicativo pessoas (que são os mesmos contatos que aqueles acessíveis no Outlook) são armazenados na caixa de correio de um usuário.|
|Agenda de aula|Os planos criados no cronograma de classe são armazenados na caixa de correio do grupo correspondente do Microsoft 365 que é provisionado quando um novo plano é criado. O alias da caixa de correio de grupo é o nome do plano.|
|Skype for Business|As conversas no Skype for Business são armazenadas na pasta de histórico de conversas da caixa de correio de um usuário. Se a caixa de correio de um participante de uma reunião do Skype for colocada em retenção de litígio ou atribuída a uma política de retenção, os arquivos anexados a uma reunião serão mantidos na caixa de correio dos participantes.|
|Sway|Os sways são armazenados como um arquivo HTML anexado a uma mensagem de email e armazenados em uma pasta oculta na caixa de correio do usuário que criou o Sway. Quando você exporta conteúdo do Sway em um arquivo PST, esses dados ficam localizados na pasta **ApplicationDataRoot** em uma subpasta chamada com o GUID a seguir) **905fcf26-4EB7-48a0-9ff0-8dcc7194b5ba**.|
|Tarefas|Tarefas no aplicativo tarefas (que são as mesmas tarefas que aquelas acessíveis no Outlook) são armazenadas na caixa de correio de um usuário.|
|Teams|As conversas que fazem parte de um canal do teams são associadas à caixa de correio do teams. As conversas que fazem parte da lista de bate-papo no Teams (também chamadas de *1 x N chats*) são associadas à caixa de correio dos usuários que participam do chat. Além disso, as informações resumidas para reuniões e chamadas em um canal do teams são associadas a caixas de correio de usuários que discaram para a reunião ou chamada. Portanto, ao pesquisar o conteúdo do Microsoft Teams, você pesquisará a caixa de correio do Microsoft Teams em conversas do canal e pesquisará as caixas de correio do usuário em um chat de 1 x N.| 
|Tarefa pendente|Tarefas (chamadas *para no dos*, que são salvas em listas de tarefas pendentes) no aplicativo de tarefas pendentes são armazenadas na caixa de correio de um usuário.|
|Yammer|Conversas e comentários em uma comunidade do Yammer estão associados à caixa de correio de grupo do Microsoft 365, bem como à caixa de correio do usuário do autor e de qualquer destinatário nomeado (@mentioned ou usuários do cc'ed). As mensagens privadas enviadas fora de uma comunidade do Yammer são armazenadas na caixa de correio dos usuários que participam da mensagem privada.|  
||||

> [!NOTE]
> No momento, se uma retenção for colocada em uma caixa de correio (usando isenções em descoberta eletrônica e casos de descoberta eletrônica avançada), o conteúdo de formulários e Sway não será preservado pela retenção. 
