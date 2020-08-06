---
title: Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Saiba como oferecer ao usuário o direito de acessar a caixa de correio de outro usuário. Isso dará ao usuário o direito de ler e enviar emails da caixa de correio do outro usuário. '
ms.openlocfilehash: 0b6977efbd6041a11c67ed66c9b7ecc72a38bde4
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560370"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores

Como administrador, talvez você tenha requisitos da empresa para permitir que alguns usuários acessem a caixa de correio de outro usuário. Por exemplo, talvez você queira habilitar um assistente para enviar ou ler emails da caixa de correio do gerente ou habilitar um dos usuários para enviar emails em nome de outro usuário. Este tópico mostra como fazer isso.
  
Se você estiver procurando informações sobre como criar e gerenciar caixas de correio compartilhadas, confira o artigo [Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Deseja configurar permissões de caixa de correio?

Com as permissões da caixa de correio, você dá acesso de leitura/gravação de uma caixa de correio a outro usuário. Os artigos a seguir ajudam você a configurar e usar esse recurso:
  
 **Configurando as permissões:**
  
a primeira etapa para configurar permissões é decidir quais ações você deseja permitir que o outro usuário realize em determinada caixa de correio. Você pode permitir que um usuário leia os emails na caixa de correio, envie emails em nome de outro usuário e envie emails como se eles fossem enviados por essa caixa de correio. Confira os seguintes artigos sobre a configuração de cada tipo de permissão:
  
- [Ler emails da caixa de correio de outro usuário](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Enviar emails da caixa de correio de outro usuário](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Enviar emails em nome de outro usuário](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Propagação das alterações:**
  
depois de configurar as permissões, pode levar até 60 minutos para que as alterações se propaguem pelo sistema e entrem em vigor.
  
 **Como usá-la após as permissões serem definidas:**
  
Há algumas maneiras diferentes que você pode acessar uma caixa de correio. Para ajuda sobre isso, confira este artigo: [Acessar a caixa de correio de outra pessoa](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).

> [!NOTE]
> As permissões só podem ser configuradas no locatário atual da organização. Não é possível configurar permissões da caixa de correio com usuários fora do locatário.
  
## <a name="send-email-from-another-users-mailbox"></a>Enviar emails da caixa de correio de outro usuário

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  
    
2. Selecione o nome do usuário (do qual você pretende fornecer uma permissão de envio) para abrir o painel Propriedades.
    
3. Na guia **email**, selecione**gerenciar permissões de caixa de correio**.

4. Ao lado de **enviar como**, selecione **editar**. 

5. Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar. 
    
6. Selecione **Salvar**.
 
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.

3. Ao lado de **enviar como**, selecione **editar**. 

4. Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar. 
    
5. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.

3. Ao lado de **enviar como**, selecione **editar**. 

4. Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar. 
    
5. Selecione **Salvar**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Ler emails na caixa de correio de outro usuário

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  
    
2. Selecione o nome do usuário (cuja caixa de correio deseja permitir a leitura) para abrir o painel propriedades dela.
    
3. Na guia **email**, selecione**gerenciar permissões de caixa de correio**.
    
4. Ao lado de **ler e gerenciar**, selecione **editar**. 
    
5. Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

6. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  
  
2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.
    
3. Ao lado de **ler e gerenciar**, selecione **editar**. 
    
4. Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

5. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 
  
2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.
    
3. Ao lado de **ler e gerenciar**, selecione **editar**. 
    
4. Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

5. Selecione **Salvar**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Enviar emails em nome de outro usuário

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  

2. Selecione o nome do usuário (do qual você planeja atribuir uma **permissão de envio**) para abrir o painel Propriedades.
    
3. Na guia **email**, selecione**gerenciar permissões de caixa de correio**.
    
4. Ao lado de **enviar em nome**, selecione **editar**.

5. Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

6. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.

3. Ao lado de **enviar em nome**, selecione **editar**.
    
4. Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

5. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.

3. Ao lado de **enviar em nome**, selecione **editar**.
    
4. Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

5. Selecione **Salvar**.

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>Enviar e ler pelo Outlook e pelo Outlook na Web para empresas


Deseja saber como enviar emails da caixa de correio de outro usuário? Confira os seguintes tópicos:
  
- [Gerenciar o email e os itens de calendário de outra pessoa](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Enviar emails de outra pessoa ou grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
