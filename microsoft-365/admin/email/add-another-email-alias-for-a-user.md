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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Saiba como você pode ter mais de um endereço de email, chamado alias de email, associado à sua conta do Microsoft 365 para empresas. '
ms.openlocfilehash: a44271cdbf52136e61702697a960cc3cbcd8119d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470996"
---
# <a name="add-another-email-alias-for-a-user"></a>Adicionar outro alias de email para um usuário
  
Este artigo é para administradores do Microsoft 365 que têm assinaturas comerciais. Ele não se destina a usuários domésticos.
  
Um endereço de email principal no Microsoft 365 geralmente é o endereço de email que um usuário foi atribuído quando sua conta foi criada. Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email. Eles também podem ter mais de um endereço de email associado à conta do Microsoft 365 para empresas. Esses endereços adicionais são chamados também de alias. 
  
Por exemplo, digamos que Ela tenha o endereço de email jenna@contosoco.com, mas também deseja receber emails no jen@contosoco.com porque algumas pessoas se referem a ela por esse nome. Você pode criar aliases para ela para que ambos os endereços de email acessem a caixa de entrada de Irene.
<br><br>  
  
Você pode criar até 400 aliases para um usuário. Não são necessárias tarifas ou licenças adicionais.
  
> [!Tip]
> Se você quiser que várias pessoas gerenciem emails enviados para um único endereço de email, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada. Para saber mais, confira [Criar uma caixa de correio compartilhada.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>Adicionar aliases de email a um usuário
<a name="AddEmailPreview"> </a>

Você deve ter [permissões de administrador](../add-users/about-admin-roles.md) para fazer isso. 

  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário > **Gerenciar aliases de email.** Você não verá essa opção se a pessoa não tiver uma licença atribuída a ela. 
    
3. Selecione **+ Adicionar um alias** e insira um novo alias para o usuário.   
    
    > [!Important] 
    > Se você receber a mensagem de erro " Um parâmetro não pode ser encontrado que corresponde ao nome do parâmetro **'EmailAddresses**", isso significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
    
  
    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Microsoft 365](../setup/add-domain.md). 
  
     
5. Quando terminar, escolha Salvar **alterações.**
    
6. Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365.
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal de Eliza Hoffman, Eliza@NodPublishers.com, e seu alias, Sales@NodPublishers.com, irão para a Caixa de Entrada de Eliza.
    
  
7. **Quando o usuário responder, o *endereço From*  será seu alias de email principal.** Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com, e ela chega na caixa de entrada de Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como remetente, não Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>. 
    
    
2. Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.

3. Ao lado de **Nome de Usuário /Aliases de Email,** selecione **Editar**.

    > [!Important] 
    > Se você receber a mensagem de erro " Um parâmetro não pode ser encontrado que corresponde ao nome do parâmetro **'EmailAddresses**", isso significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.

4. Na caixa de texto em **Alias**, digite a primeira parte do novo alias de email. Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa. Em seguida, selecione **OK**.

    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Microsoft 365](../setup/add-domain.md). 

5. Quando terminar, selecione **Salvar**.

6. Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365. 
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal de Eliza Hoffman, Eliza@NodPublishers.com, e seu alias, Sales@NodPublishers.com, irão para a Caixa de Entrada de Eliza.
    
  
7. **Quando o usuário responder, o *endereço From*  será seu alias de email principal.** Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com, e ela chega na caixa de entrada de Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como remetente, não Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

    
2. Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.

3. Ao lado de **Nome de Usuário /Aliases de Email,** selecione **Editar**.

    > [!Important] 
    > Se você receber a mensagem de erro " Um parâmetro não pode ser encontrado que corresponde ao nome do parâmetro **'EmailAddresses**", isso significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.

4. Na caixa de texto em **Alias**, digite a primeira parte do novo alias de email. Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa. Em seguida, selecione **OK**.

    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Microsoft 365](../setup/add-domain.md). 

5. Quando terminar, selecione **Salvar**.

6. Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365. 
    
    O usuário agora terá um endereço principal e um alias. Por exemplo, todos os emails enviados para o endereço principal de Eliza Hoffman, Eliza@NodPublishers.com, e seu alias, Sales@NodPublishers.com, irão para a Caixa de Entrada de Eliza.
    
  
7. **Quando o usuário responder, o *endereço From*  será seu alias de email principal.** Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com, e ela chega na caixa de entrada de Eliza. Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como remetente, não Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Você conseguiu "Um parâmetro não pode ser encontrado que corresponde ao nome do parâmetro EmailAddresses"?


Se você receber a mensagem de erro " Um parâmetro não pode ser encontrado que corresponde ao nome do parâmetro **EmailAddresses**" significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Você comprou a assinatura da GoDaddy ou de outro parceiro?


Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.
  
## <a name="related-articles"></a>Artigos relacionados

[Enviar email de um endereço diferente](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Alterar um nome de usuário e endereço de email](../add-users/change-a-user-name-and-email-address.md)
