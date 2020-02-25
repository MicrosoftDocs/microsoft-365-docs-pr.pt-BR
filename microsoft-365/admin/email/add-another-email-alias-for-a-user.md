---
title: Adicionar outro alias de email para um usuário
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Saiba como você pode ter mais de um endereço de email, chamado alias de email, associado à sua conta do Office 365 para empresas. '
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250691"
---
# <a name="add-another-email-alias-for-a-user"></a>Adicionar outro alias de email para um usuário
  
Este artigo é para os administradores do Office 365 que têm assinaturas de negócios. Ele não se destina a usuários domésticos.
  
Um endereço de email principal no Office 365 geralmente é o endereço de email que um usuário recebeu quando a conta foi criada. Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email. Ele pode ter mais de um endereço de email associado à respectiva conta do Office 365 para empresas. Esses endereços adicionais são chamados também de alias. 
  
Por exemplo, digamos que Jenna tenha o endereço de email jenna@contosoco.com, mas ele também deseja receber emails em jen@contosoco.com porque algumas pessoas se referem a ele por esse nome. Você pode criar aliases para que os dois endereços de email vá para a caixa de entrada do Jenna.
<br><br>  
  
Você pode criar até 400 aliases para um usuário. Não são necessárias tarifas ou licenças adicionais.
  
> [!Tip]
> Se você quiser que várias pessoas gerenciem emails enviados para um único endereço de email, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada. Para saber mais, confira [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Adicionar aliases de email a um usuário
<a name="AddEmailPreview"> </a>

Você deve ter [permissões de administrador](../add-users/about-admin-roles.md) para fazer isso. 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos** , selecione o usuário > **gerenciar aliases de email**. Você não verá essa opção se a pessoa não tiver uma licença atribuída a elas. 
    
3. Selecione **+ Adicionar um alias** e insira um novo alias para o usuário.   
    
    > [!Important] 
    > Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
    
  
    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx). 
  
     
5. Quando terminar, escolha **salvar alterações**.
    
6. Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.
    
  
7. **Quando o usuário responder, o endereço de será seu alias *de* email principal.** Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>. 
    
    
2. Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.

3. Ao lado de **nome de usuário/alias de email**, selecione **Editar**.

    > [!Important] 
    > Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.

4. Na caixa de texto em **alias**, digite a primeira parte do novo alias de email. Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa. Em seguida, selecione **Adicionar**.

    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx). 

5. Quando terminar, selecione **salvar**.

6. Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365. 
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.
    
  
7. **Quando o usuário responder, o endereço de será seu alias *de* email principal.** Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

    
2. Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.

3. Ao lado de **nome de usuário/alias de email**, selecione **Editar**.

    > [!Important] 
    > Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.

4. Na caixa de texto em **alias**, digite a primeira parte do novo alias de email. Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa. Em seguida, selecione **Adicionar**.

    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx). 

5. Quando terminar, selecione **salvar**.

6. Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365. 
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.
    
  
7. **Quando o usuário responder, o endereço de será seu alias *de* email principal.** Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Você obteve "não foi possível encontrar um parâmetro que corresponda ao nome de parâmetro EmailAddresses"?


Se você receber a mensagem de erro "**não é possível localizar um parâmetro que coincida com o nome do parâmetro EmailAddresses**" significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado se você tiver adicionado um pouco mais. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Você comprou a assinatura da GoDaddy ou de outro parceiro?


Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.
  
## <a name="related-articles"></a>Artigos relacionados

[Enviar email de um endereço diferente](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[Alterar um nome de usuário e endereço de email](../add-users/change-a-user-name-and-email-address.md)
  

