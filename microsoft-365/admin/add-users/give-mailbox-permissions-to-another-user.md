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
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780596"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores

Como administrador, talvez você tenha requisitos da empresa para permitir que alguns usuários acessem a caixa de correio de outro usuário. Por exemplo, talvez você queira habilitar um assistente para enviar ou ler emails da caixa de correio do gerente ou habilitar um dos usuários para enviar emails em nome de outro usuário. Este tópico mostra como fazer isso.
  
Se você estiver procurando informações sobre como criar e gerenciar caixas de correio compartilhadas, confira o artigo [Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Deseja configurar permissões de caixa de correio?

Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:
  
 **Configurando as permissões:**
  
The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:
  
- [Ler emails da caixa de correio de outro usuário](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Enviar emails da caixa de correio de outro usuário](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Enviar emails em nome de outro usuário](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Propagação das alterações:**
  
depois de configurar as permissões, pode levar até 60 minutos para que as alterações se propaguem pelo sistema e entrem em vigor.
  
 **Como usá-la após as permissões serem definidas:**
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)
  
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


Want to know how to send email from another user's mailbox? Check out the following topics:
  
- [Gerenciar o email e os itens de calendário de outra pessoa](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Enviar emails de outra pessoa ou grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
