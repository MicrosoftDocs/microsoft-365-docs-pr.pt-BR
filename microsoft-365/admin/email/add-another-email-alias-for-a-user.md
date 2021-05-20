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
description: 'Saiba como você pode ter mais de um endereço de e-mail, chamado de pseudônimo de e-mail, associado ao seu Microsoft 365 para conta de negócios. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572100"
---
# <a name="add-another-email-alias-for-a-user"></a>Adicionar outro alias de email para um usuário
  
Este artigo é para administradores Microsoft 365 que possuem assinaturas de negócios. Ele não se destina a usuários domésticos.
  
Um endereço de e-mail principal em Microsoft 365 geralmente é o endereço de e-mail que um usuário foi atribuído quando sua conta foi criada. Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email. Eles também podem ter mais de um endereço de e-mail associado ao seu Microsoft 365 para conta de negócios. Esses endereços adicionais são chamados também de alias. 
  
Por exemplo, digamos que Jenna tem o endereço de e-mail jenna@contosoco.com, mas ela também quer receber e-mails em jen@contosoco.com porque algumas pessoas se referem a ela com esse nome. Você pode criar codinomes para ela para que ambos os endereços de e-mail vão para a caixa de entrada da Jenna.
  
Você pode criar até 400 aliases para um usuário. Não são necessárias tarifas ou licenças adicionais.
  
> [!Tip]
> Se você quiser que várias pessoas gerenciem e-mails enviados para um único endereço de e-mail, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada. Para saber mais, consulte [Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Adicionar aliases de email a um usuário

Você deve ter [permissões administrativas](../add-users/about-admin-roles.md) para fazer isso. 

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **Usuários Ativos,** selecione o usuário > **Gerenciar o nome de usuário e o e-mail**. Você não verá essa opção se a pessoa não tiver uma licença atribuída a ela. 
    
3. Selecione **+ Adicione um pseudônimo** e digite um novo pseudônimo para o usuário.   
    
    > [!Important] 
    > Se você receber a mensagem de erro "**Um parâmetro não pode ser encontrado que corresponda ao nome do parâmetro 'EmailAddresses**", significa que está demorando um pouco mais para terminar de configurar seu inquilino ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
    
  
    > [!IMPORTANT]
    > Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal. 
  
    > [!TIP]
    > O alias de email deve terminar com um domínio da lista suspensa. Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio a Microsoft 365](../setup/add-domain.md). 
  
     
5. Quando terminar, escolha **Salvar alterações**.
    
6. Espere 24 horas para os novos pseudônimos povoarem ao longo de Microsoft 365.
    
    O usuário agora terá um endereço principal e um pseudônimo. Por exemplo, todas as correspondências enviadas para o endereço principal de Eliza Hoffman, Eliza@NodPublishers.com, e seu pseudônimo, Sales@NodPublishers.com, irão para a Caixa de Entrada de Eliza.
    
  
7. **Quando o usuário responder, o endereço *From* dependerá de seu Outlook cliente. Outlook na web usarão o pseudônimo em que o e-mail foi recebido (vamos chamar isso de princípio do ping-pong). Outlook desktop usará seu pseudônimo principal de e-mail.** Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com, e chega na caixa de entrada de Eliza. Quando Eliza responder à mensagem usando Outlook desktop, seu endereço de e-mail principal aparecerá como Eliza@NodPublishers.com, não Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Você conseguiu "Um parâmetro não pode ser encontrado que corresponda ao nome de parâmetro EmailAddresses"?

Se você receber a mensagem de erro "**Um parâmetro não pode ser encontrado que corresponda ao nome do parâmetro EmailAddresses**" significa que está demorando um pouco mais para terminar de configurar seu inquilino ou seu domínio personalizado se você adicionou um recentemente. O processo de configuração pode levar até quatro horas para ser concluído. Aguarde um pouco até ele terminar e tente novamente. Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Você comprou a assinatura da GoDaddy ou de outro parceiro?


Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.

## <a name="sending-email-from-the-proxy-address-easily"></a>Enviando e-mails do endereço proxy facilmente

Um novo recurso será lançado em abril de 2021 que permite que os usuários enviem seus pseudônimos facilmente ao usar Outlook na web. Quando o recurso é lançado para uma locação onde o administrador inquilino usa o `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, os usuários dentro da locação terão acesso a uma lista de caixas de seleção onde cada entrada corresponde a um pseudônimo em suas configurações de Outlook. A seleção de um alia fará com que ele apareça no formulário De dropdown no formulário Compor.
  
## <a name="related-content"></a>Conteúdo relacionado

[Enviar e-mails de um endereço diferente](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artigo)

[Alterar um nome de usuário e endereço de e-mail](../add-users/change-a-user-name-and-email-address.md) (artigo)

[Configurar o encaminhamento de email no Microsoft 365](configure-email-forwarding.md) (artigo)
