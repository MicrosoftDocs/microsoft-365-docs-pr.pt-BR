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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Conceder a um usuário o direito de acessar a caixa postal de outro usuário, o que permite ao usuário ler e enviar emails da caixa postal do outro usuário.
ms.openlocfilehash: 3514be02f2ef82b727edfcf86c0bd3f6b8515510
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535957"
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
    
3. Na guia **email**, selecione **gerenciar permissões de caixa de correio**.

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
    
3. Na guia **email**, selecione **gerenciar permissões de caixa de correio**.
    
4. Ao lado de **ler e gerenciar**, selecione **editar**. 
    
5. Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.

6. Selecione **Salvar**.


> [!NOTE]
> As permissões de **Leitura** e **Gerenciamento** são chamadas de permissão de **Acesso Total** quando concedidas no Centro de administração do Exchange. A permissão de Acesso Total não concede as permissões **Enviar como** ou **Enviar em Nome de**.

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
    
3. Na guia **email**, selecione **gerenciar permissões de caixa de correio**.
    
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


## <a name="related-content"></a>Conteúdo relacionado
  
[Gerenciar o email e os itens de calendário de outra pessoa](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (artigo)
    
[Enviar emails de outra pessoa ou grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (artigo)

[Alterar um nome de usuário e endereço de email](../add-users/change-a-user-name-and-email-address.md) (vídeo)

