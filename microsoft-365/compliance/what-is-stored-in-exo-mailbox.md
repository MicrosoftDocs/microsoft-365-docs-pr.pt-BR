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
description: Os dados produzidos por aplicativos baseados em nuvem no Office 365 são armazenados na caixa de correio do Exchange Online de um usuário no Microsoft Cloud.
ms.openlocfilehash: f9db94eebf855a2d8dcfee8897ca6171eabbc400
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597188"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Conteúdo armazenado em caixas de correio do Exchange Online

Uma caixa de correio no Exchange Online é usada principalmente para armazenar itens relacionados a email, como mensagens, itens de calendário, tarefas e anotações. Mas isso está mudando como mais aplicativos do Office 365 baseados em nuvem também armazenam seus dados na caixa de correio de um usuário. Uma vantagem de armazenar dados em uma caixa de correio é que você pode usar as ferramentas de pesquisa em pesquisa de conteúdo, descoberta eletrônica, descoberta eletrônica avançada e investigações de dados para localizar, exibir e exportar os dados desses aplicativos baseados em nuvem. Os dados de alguns desses aplicativos são armazenados em pastas ocultas localizadas em uma subárvore de mensagens não interpessoais (não-IPM) na caixa de correio. Isso significa que os dados ficam ocultos do modo de exibição do usuário quando eles usam o Outlook ou outros clientes de email para acessar sua caixa de correio.

A tabela a seguir lista os aplicativos do Office 365 que armazenam dados em uma caixa de correio baseada em nuvem. A tabela também descreve o tipo de conteúdo que cada aplicativo armazena.

|Aplicativo do Office 365  |Descrição  |
|:---------|:---------|
|Forms     <br/> |Formulários (armazenados como um arquivo PDF) e respostas a um formulário (armazenado em um arquivo CSV) são anexados a mensagens de email e armazenadas em uma pasta oculta na caixa de correio do usuário que criou o formulário. Quando você exporta conteúdo de formulários em um arquivo PST, esses dados estão localizados na pasta **ApplicationDataRoot** em uma subpasta chamada com o seguinte identificado globalmente exclusivo (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.        <br/> |
|Grupos do Office 365    <br/>|  Mensagens de email, itens de calendário, contatos (pessoas), anotações e tarefas são armazenados na caixa de correio associada a um grupo do Office 365.       <br/> |
|Outlook/Exchange Online<br/>|  Mensagens de email, itens de calendário, contatos (pessoas), anotações e tarefas são armazenados na caixa de correio de um usuário.       <br/> |
|Pessoas    <br/> |  Contatos no aplicativo pessoas (que são os mesmos contatos que aqueles acessíveis no Outlook) são armazenados na caixa de correio de um usuário.      <br/> |
|Agenda de aula     <br/> |   Os planos criados no cronograma de classe são armazenados na caixa de correio do grupo do Office 365 correspondente que é provisionado quando um novo plano é criado. O alias da caixa de correio de grupo é o nome do plano.      <br/> |
|Skype for Business    <br/>  | As conversas no Skype for Business são armazenadas na pasta de histórico de conversas da caixa de correio de um usuário. Se a caixa de correio de um participante de uma reunião do Skype for colocada em retenção de litígio ou atribuída a uma política de retenção, os arquivos anexados a uma reunião serão mantidos na caixa de correio dos participantes.         <br/> |
|Sway     <br/> |  Os sways são armazenados como um arquivo HTML anexado a uma mensagem de email e armazenados em uma pasta oculta na caixa de correio do usuário que criou o Sway. Quando você exporta conteúdo do Sway em um arquivo PST, esses dados ficam localizados na pasta **ApplicationDataRoot** em uma subpasta chamada com o GUID a seguir) **905fcf26-4EB7-48a0-9ff0-8dcc7194b5ba**.       <br/> |
|Tarefas    <br/> |  Tarefas no aplicativo tarefas (que são as mesmas tarefas que aquelas acessíveis no Outlook) são armazenadas na caixa de correio de um usuário.       <br/> |
|Teams    <br/>  |As conversas que fazem parte de um canal do teams são armazenadas na caixa de correio associada à equipe. As conversas que fazem parte da lista de bate-papo no Teams (também chamadas de *1 x N chats*) são armazenadas na caixa de correio dos usuários que participam do chat. Além disso, as informações resumidas para reuniões e chamadas em um canal do teams são armazenadas nas caixas de correio dos usuários que discaram para a reunião ou chamada. <br/> | 
|Tarefa pendente  <br/> | Tarefas (chamadas *para no dos*, que são salvas em listas de tarefas pendentes) no aplicativo de tarefas pendentes são armazenadas na caixa de correio de um usuário.        <br/> |
||||

> [!NOTE]
> No momento, se uma retenção for colocada em uma caixa de correio (usando isenções em descoberta eletrônica e casos de descoberta eletrônica avançada), o conteúdo de formulários e Sway não será preservado pela retenção. 