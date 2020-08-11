---
title: 'Gerenciar sua rede de gerenciamento de conhecimento (versão prévia) '
description: Como configurar o gerenciamento de conhecimento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: af53f4d563d286ad29138f935fbb69aa10b902ca
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612615"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Gerenciar sua rede de gerenciamento de conhecimento (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).


Depois de [Configurar o gerenciamento de conhecimento](set-up-knowledge-network.md), a qualquer momento depois, um administrador pode fazer ajustes nas suas definições de configuração através do centro de administração do Microsoft 365.

Por exemplo, você pode precisar ajustar suas configurações para qualquer um dos seguintes:
- Adicione novas fontes do SharePoint aos tópicos de meus.
- Alterar quais usuários terão acesso aos tópicos.
- Alterar quais usuários têm permissões para executar tarefas no centro de tópicos.
- Alterar o nome do seu centro de tópico


## <a name="requirements"></a>Requisitos 
Você deve ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e gerenciar tarefas de conhecimento organizacional.


## <a name="to-access-knowledge-management-settings"></a>Para acessar as configurações de gerenciamento de conhecimento:

1. No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .
2. Na seção **conhecimento organizacional** , clique em **conectar pessoas a conhecimento**.<br/>

    ![Conectar pessoas a conhecimento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Na página **conectar pessoas a conhecimento** , selecione **gerenciar** para abrir o painel **configurações de rede de conhecimento** .<br/>

    ![conhecimento-rede – configurações](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Alterar o modo como a rede de conhecimento pode encontrar tópicos

Selecione a guia **descoberta de tópico** se quiser atualizar suas escolhas para as fontes de tópico do SharePoint. Essa configuração permite que você selecione os sites do SharePoint em seu locatário que serão rastreados e extraídos para tópicos.

1. Na guia **descoberta de tópico** , em **selecionar fontes de tópicos do SharePoint**, selecione **Editar**.
2. Na página **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta. Isso inclui:</br>
    a. **Todos os sites**: todos os sites do SharePoint em seu locatário. Isso captura sites atuais e futuros.</br>
    b. **Todos, exceto sites selecionados**: digite os nomes dos sites que você deseja excluir.  Você também pode carregar uma lista de sites que deseja recusar da descoberta. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. </br>
    c. **Somente sites selecionados**: digite os nomes dos sites que você deseja incluir. Você também pode carregar uma lista de sites. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos. </br>

    ![Escolher como localizar tópicos](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Se você tiver um número de sites que você deseja excluir (se você selecionar **todos, exceto os sites selecionados**) ou incluir (se você selecionou **apenas sites selecionados**), poderá optar por carregar um arquivo CSV com os nomes e URLs dos sites. Você pode selecionar **baixar modelo de site. csv** se quiser usar o arquivo de modelo CSV.

3. Selecione **Salvar**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Alterar quem pode ver os tópicos em sua organização

Selecione a guia **descoberta de tópico** se você deseja atualizar quem em sua organização pode ver tópicos descobertos nos resultados da pesquisa e quando os tópicos estão realçados em conteúdo como páginas do SharePoint.

1. Na guia **descoberta de tópicos** , em **quem pode ver os tópicos na rede de conhecimento**, selecione **Editar**.
2. Na página **quem pode ver os tópicos da página da rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos. Você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Apenas pessoas ou grupos de segurança selecionados**</br>
    c. **Ninguém**</br>

    ![Quem pode ver os tópicos](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Selecione **Salvar**.  
 
> [!Note] 
> Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de gerenciamento de conhecimento atribuídas poderão exibir tópicos.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Alterar quem tem permissões para executar tarefas no centro de tópicos

Selecione a guia **permissões de tópico** se quiser atualizar quem tem permissões para fazer o seguinte na página central de tópicos:

- Quais usuários podem criar e editar tópicos: criar novos tópicos que não foram encontrados durante a descoberta ou editar detalhes da página de tópico existente.
- Quais usuários podem gerenciar tópicos: confirmar ou rejeitar tópicos descobertos.

Para atualizar as permissões para criar e editar tópicos:

1. Na guia **permissões de tópico** , em **quem pode criar e editar tópicos**, selecione **Editar**.</br>
2. Na página **quem pode criar e editar tópicos** , você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Apenas pessoas ou grupos de segurança selecionados**</br>

    ![Criar e editar tópicos](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Selecione **Salvar**.</br>

Para atualizar as permissões para gerenciar tópicos:

1. Na guia **permissões de tópico** , em **quem pode gerenciar tópicos**, selecione **Editar**.</br>
2. Na página **quem pode gerenciar os tópicos** , você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Pessoas ou grupos de segurança selecionados**</br>

    ![Gerenciar tópicos](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Selecione **Salvar**.</br>


##  <a name="update-your-topic-center-name"></a>Atualizar o nome da central de tópicos

Selecione a guia **central de tópicos** se você deseja atualizar o nome do seu centro de tópico. 

1. Na guia **central de tópicos** , em **nome da central de tópicos**, selecione **Editar**.
2. Na página **Editar nome da central de tópicos** , na caixa **nome da central de tópicos** , digite o novo nome para o seu centro de tópico.
3. Selecione **Salvar**

    ![Editar nome da central de tópicos](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Confira também



  






